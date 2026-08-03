## 目錄

- [額外問題](#額外問題)
- [CI/CD](#cicd)
- [SpringFramework](#springframework)
- [服務異常](#服務異常)
- [專業知識基礎](#專業知識基礎)
- [Unit Test](#unit-test)
- [Java Heap Analysis](#java-heap-analysis)
- [Complex Configuration](#complex-configuration)
- [Parser](#parser)
- [Web MVC](#web-mvc)
- [Database Optimization](#database-optimization)
- [爬蟲](#爬蟲)
- [Internal Fragmentation](#internal-fragmentation)

## 額外問題

* 背景：彩票系統
    * Java, SpringFramework
* 情境：
    * 會議上討論壓力測試不過的功能
    * 決定先關閉特定功能，確保該功能為瓶頸
* 發現問題過程：
    * 在此之前，我已先閱讀該程式碼
    * QA 建議可先從介面上關閉該功能
    * 我從已知記憶中，發現該功能的實作沒有考慮關閉該功能的情況
    * QA 確認關閉的功能沒有實作，會造成出金限制
* 心得：在 AI 的年代，閱讀程式碼似乎沒有效率，但對系統的理解可能在其它情境，發現新的 Bug

## CI/CD

* 背景：彩票系統
    * 使用自架 Gitlab
    * 使用自架 Maven Nexus
* 問題：
    * 六個微服務需要十分鐘，dev 環境才能完成部屬
* 其它負作用
    * DevOp 發現 Nexus 額度滿載，造成全公司都無法 build
        * 架設兩台 Nexus，並以團隊區分，使用不同的 Nexus
    * 每個工程師平均一天更新六次，就花了一小時在等待 CI/CD
* 解決：
    * 個人工作的空檔，了解該原因，發現二個問題
        1. Maven Repository 在 Gitlab CI/CD 快取沒有設定正確，造成每次 build 都重新抓取
        1. 同樣的 `mvn compile` 執行了兩次
    * 調整為合理的運作
    * 二分半鐘完成部屬
* 心得：看似次要的小事，可能造成團隊不同部門的成本

## SpringFramework

* 背景：彩票系統
    * 使用 _Mybatis Flex_ 為 ORM
* 問題：
    * A 同事發現與 SpringFramework `@Transactional` 的整合有問題
    * 我在開發資料庫單元測試(`DataJpaTest`)，也發現了不會自動 Rollback
* 解決：
    * 我決定看 Mybatis Flex 的 source code，發現他會用自己的 _Data Source_ wrap 預設的 _Data Source_，
        造成 `@Transactional` 的行為不一致
    * 以 Mybatis Flex 的 _Data Source_ 作為 Spring Context 的預設 context
* 後續：
    * 壓力測試 10 萬下單，修改前測試不過，修改後測試成功
* 心得：
    * 程式面基礎架構影響層面重大，需要確保 framework 的使用與預期行為正確

## 服務異常

* 背景：虛擬貨幣交易所
    * Java, SpringFramework
* 問題：
    * DevOp 發現正式環境，HTTP Request 有時候會沒法處理，但訊息不明確
    * 系統依然在運作，看似隨機行為
* 處理：
    * HTTP Log 只給 5xx 的訊息，但沒有其它資訊
    * 微服務的 Log 沒有任何錯誤，看似沒有收到發生錯誤的 HTTP request
    * 協同 DevOp 先進入 nginx 查 log
    * 發現 _ulimit_ too many open file
* 心得：查詢問題時，需要全盤考量，逐一拆解

## 專業知識基礎

* 背景：虛擬貨幣交易所
    * Java, SpringFramework
* 問題：
    * A 同事開發的微服務，DevOp 反應開了 16 核的 VM，還是來不及處理要儲存進資料的行情資料
    * B 同事繼續在該模組上開發功能，發現許多缺資料的問題
* 原因：
    * 該模組每一批行情收到後，建立新的 Java Executor，然後關閉
* 處理：
    * 建議 B 同事調整多執行緒策略，並把程式改為 Batch of buffered Queue 的方式寫進資料庫
* 結果：
    * 降至四核 VM，該微服務平均 CPU 用量約為 20%
* 心得：多執行緒的使用方式與資料庫大量寫入專業知識基礎極為重要

## Unit Test

* 背景：虛擬貨幣交易所
    * Java, SpringFramework
* 問題：
    * A 同事負責處理弱點掃描後，制換需要被取代的加密函式
        * 函式為回傳 *base 64* 字串
    * 但只測試幾個功能
    * 上版後，造成出入金失敗
* 原因：新的函式回傳大小寫不同，A 同事剛好只測到 `equalsIgnoreCase()` 的功能
* 個人：
    * 我在前不久也因重構，處理別的類似功能
    * 我採用 TDD 方式，先寫測試
* 後續：
    * 在 Retrospective Meeting 上，我分享了自己的做法，確保原有功能正確
    * 同時也分享加密的內容驗證可以直接比對二進位元，避免字串大小寫的情況
* 心得：
    * 很簡單的單元測試，可以確保系統關鍵功能的正確性

## Java Heap Analysis

* 背景：虛擬貨幣交易所
    * Java, SpringFramework
* 問題：
    * A 同事開發的功能，一直會造成 Java 微服務關閉
* 協助處理：
    * 查訊息後，發現是 HEAP Out of memory
    * Dump JVM HEAP 後，透過 VisualVM，發現是該版 hibernate 會對每個不同數量的 `WHERE prop IN (?)`
        產生抽象語法樹(AST)，造成記憶用量隨著系統用量逐漸增加

## Complex Configuration

* 背景：虛擬貨幣交易所
    * Java, SpringFramework
* 工作：準備將目前手動部屬在 VM 裡的 JVM microservice 轉移到 K8S
* 問題：
    * 組態由後端開發者提供，更新時由 Tech Leader 比對 Git Files，提供要更動的組態
    * DevOp 同事更新時，處理要更新的組態
    * 時常人為出錯
* 處理：
    * 區分與環境相關與無關的組態，簡化部屬真正需要的組態
    * 由 40 ~ 50 降至 4 ~ 10
* 後續：由於其它情況，DevOp 沒有時間進行 K8S 轉移
* 好處：DevOp 在原有部屬的情況簡化並不再容易出現人為出錯的情況

## Parser

* 背景：KYC 系統
* 問題：
    * 法院判決書為整篇 pdf 轉為單一 JSON property(以換行符號分隔)
    * 有多種公文格式
    * 原有功能使用非同步查詢，每次都要查詢 40 GB 的 JSON 全文資料
    * 運作成本太高
* 解決方式：
    * 開發 Parser(2-phase)，建立 KYC 所需的索引

## Web MVC

* 背景：CDN 監控系統
    * 使用 GoLang, MySQL
    * 使用 _gin_ 做為框架
* 動機：為了簡化開發，模仿 Spring WebMVC，開發 Declarative style 的 _gin_ 延伸機制
    ```go
    engine.GET(
      "/your_get_service",
      mvcBuilder.BuildHandler(func(
            validator *validator.Validate,
            convSrv otype.ConversionService,
        v *struct {
          Name string `mvc:"query[name]"`
          Age int16 `mvc:"query[age]"`
          SessionId string `mvc:"header[owl-session-id]"`
        }
      ) string {
          // Access HTTP parameters by v.Name, v.SessionId ...

          return "OK"
      }),
    )
    ```
* 心得：SpringFramework 許多設計理念值得參照

## Database Optimization

* 背景：CDN 監控系統
    * 使用 GoLang, MySQL
    * A 同事寫的報表功能，造成 MySQL 大量 deadlock，並造成系統整個鎖死
    * B 同事負責修改該功能
* 問題：
    * 把所有資料讀進微服務計算
    * 寫入每一筆資料不斷開啟新 goroutine 執行 INSERT
* 過程：
    * B 同事尋求我的協助
    * 我建議不再從資料庫取出所有資料計算，改以建立合適的索引，並以分批(batch) 的方式建立資料
    * 對於不斷新增的監控數據，建議採用 Buffered/Interval 雙軌方式存入 MySQL
* 結果：該功運作無誤，並大大降低原有負載至 30%
* 心得：資料庫設計需要前期有完整的設計與規畫，後續造成的問題與修改成本太高

## 爬蟲

* 年代：2010 年
* 背景：E-Book 系統串接 DRM
    * DRM 為 Web UI 系統，沒有 API
* 技術: Java, SpringFramework
    * 使用 Apache HTTP Client 開發爬蟲，模擬登入/建立/取得 DRM 資訊
* 心得：
    * 熟悉 HTTP 運作是串接傳統 Web 系統的最後手段

## Internal Fragmentation

* 背景：E-Learning System(第一份工作)
* 技術：第一代微軟 ASP(VBScript)/IIS，dynamic script language
* 問題：
    * 公司自製了一支程式，可以上傳部份更新檔案，更新系統(無需重新啟用 IIS)
    * 有時候會出現 Out of memory，需要重新啟動 IIS
    * Windows 系統監控記憶是足夠的
* 如何解決：
    * 我重新閱讀 Operating System Principles 這本書關於記憶體的章節
    * Internal Fragmentation 給了我想法
    * 幸好全系統的程式都有 include 一支 `common.asp` 檔
    * 每次更新強迫更新 `common.asp`
    * 實務測試後，不再出現 Out of memory 錯誤
* 心得：電腦科學基礎永遠在最深的地方提供協助
