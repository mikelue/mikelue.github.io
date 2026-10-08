這是 [https://gh.mikelue.guru/](https://gh.mikelue.guru/)，
**請造訪網站**，以取得我的職涯與最新動態詳情。

我的電子郵件：**[mike.lue0627@msa.hinet.net](mike.lue0627@msa.hinet.net)**<br>

[English version](./README.md)：https://gh.mikelue.guru/README.md

* [工作案例](./Cases-zh.md): https://gh.mikelue.guru/Cases-zh.md
* [履歷摘要](./Summary-zh.md): https://gh.mikelue.guru/Summary-zh.md
* 我從工作缺陷中學到的[心得](./Remarks-zh.md): https://gh.mikelue.guru/Remarks-zh.md

我在工作中撰寫的部分文件可見於 [mikelue/mikelue.github.io](https://github.com/mikelue/mikelue.github.io/)。

-----

我的 GitHub：[@mikelue](https://github.com/mikelue)，個人專案：
* [mikelue/foxglove](https://github.com/mikelue/foxglove)－作為 [@Sql](https://docs.spring.io/spring-framework/docs/current/javadoc-api/org/springframework/test/context/jdbc/Sql.html) 的替代方案，此函式庫依定義的規則產生資料，而非撰寫 SQL `INSERT INTO` 陳述式。
* [mikelue/vim-maven-plugin](https://github.com/mikelue/vim-maven-plugin)－適用於 Maven 的 VIM 外掛。
* [mikelue/ddu-source-k8s](https://github.com/mikelue/ddu-source-k8s)－[DDU](https://github.com/Shougo/ddu.vim) 的來源 VIM 外掛。

-----

**目錄**

* [職涯](#職涯)
* [重要歷程](#重要歷程)
* [學歷](#學歷)
* [其他](#其他)

# 我所經歷的一些事

軟體開發：
* 無論採用何種開發流程，軟體開發都必須具備三件事：_**定義**_、_**實作**_與_**測試**_。
* 架構改善無法解決設計缺陷，設計改善無法解決實作缺陷。
* 權宜措施總是不值得的；若釋出許多權宜措施，便無法判斷是哪一個造成客戶流失。

資料設計：
* 寫程式如同開始一段關係，資料設計則如同經營婚姻。
* 資料庫隨時間推移便不再是同一個資料庫（如同婚姻）。
* 資料缺陷的成本總是高於程式碼缺陷。

測試：
* 軟體品質如同洋蔥，外層（前端）依賴內層（後端）。
* 在內層除錯的成本高於外層。
* 任何整體測試都可以且應該拆分為原子測試。

文件：
* 撰寫內容，幫助自己在未來回想可能遺忘的事物。
* 用筆書寫，以在腦中建構簡單模型。
* 有總比沒有好。

# 影響我設計原則的事物

無出處：
* *「當規格遺失時，一切也都遺失。」*
* *「預防勝於治療。」*－*Benjamin Franklin*

出自 [The Art of SQL, 978-0596008949](https://www.amazon.com/Art-SQL-Stephane-Faroult/dp/0596008945/ref=sr_1_1?keywords=the+art+of+sql&qid=1658546247&s=books&sr=1-1)：
* *「成功的資料建模，是對本質上簡單之設計原則的嚴謹運用。」*
* *「令人遺憾的事實是：當人們開始認可你是熟練的 SQL 調校者時，他們會等到發現效能問題才來徵詢意見。」*

其他書籍：
* *「Schema 最佳化與索引需要宏觀的方法，以及對細節的關注。」* \- [High Performance MySQL](https://www.amazon.com/High-Performance-MySQL-Silvia-Botros-ebook/dp/B09M7W126W/ref=sr_1_1?keywords=High+Performance+MySQL&qid=1658556030&s=books&sr=1-1)

-----

# 職涯

* 夕煇有限公司（Xihui Inc.）
## 資深後端程式設計師
2026 年 1 月～2026 年 6 月

職責：
* 開發彩券系統功能
* 設計與實作官方彩券號碼擷取服務

完成事項：
* 以 Liquibase 導入資料庫 schema 版本控制
* 為團隊共用環境導入熱置換部署
* 將 CI/CD 建置時間從 10 分鐘縮短至 2 分鐘
* 排除系統效能問題
* 解決 MyBatis Flex 造成的交易切分問題

技術堆疊：
* Java（25）：SpringBoot、Spring Data JPA、MyBatis Flex、Spring WebFlux
* 測試：Mockito、JMockit、JUnit、Instancio、AssertJ
* 佇列／資料庫：Kafka、Redis、PostgreSQL

## 資深架構師／後端程式設計師
* [TriiiX Inc.](http://www.triiix.io/)*<br>
*2022 年 9 月～2024 年 10 月*

職責：
* 分散式系統中可靠交易的技術。
* 從外部系統非同步輸入資料的技術。
* 解決 RDB 造成的系統瓶頸。
* 解決不良實作造成的系統瓶頸。

完成事項：
* 簡化 20 個後端微服務（自架）的部署。
* 將無法擴展的微服務轉為可擴展服務。
* 將舊有日誌機制轉為 GCP 結構化日誌。
* 重新實作大量 context switch 的服務。
* 使用雙層反向代理，使私有 API 易於測試。
* 將 Spring／Spring Boot 的雜亂用法重構為合宜的實作。
* 將龐雜 properties 精簡為必要設定，以簡化正式環境部署。
* 縮小 JAR 大小。

帶來的改善：
* 如何在舊系統撰寫單元測試。
* 如何使用 Spring Boot 防止將本機設定部署到共用環境。
* 如何撰寫有效的日誌訊息。

技術：
* Java：SpringFramework（Boot、Data、Message）
* Reactive Programming：Reactor、Kafka
* 測試：JUnit、Instancio
* 資料庫：MySQL、MongoDB、Liquibase
* 多執行緒：JDK Concurrent、Reactor
* 協定：HTTP、WebSocket

## 資深架構師／後端程式設計師
*重量科技股份有限公司 [KryptoGo Inc.](http://kryptogo.com/)*<br>
*2020 年 8 月～2021 年 8 月（1 年）*

負責產品：KYC（認識你的客戶）、CDD（客戶盡職調查）系統

主要職責：
* 接手既有系統
* 規劃系統架構
* 設計與實作後端服務

完成事項：
* 建置解析器，解析司法判決並建立搜尋索引。
  * 將搜尋速度從近 10 分鐘提升至即時。
* 設計 Google 搜尋引擎網頁的並行爬蟲。
* 簡化既有系統的微服務架構，使 GCP 帳單降低 50%。

### 程式開發
* Java：Java 13、Maven、Reactor、Jackson JSON
  * 使用 reactive programming（Reactor）
  * Spring：Boot、WebFlux、JPA、Redis
  * Spring Security：WebFlux Security、Session（Redis）
  * 測試：JUnit5、AssertJ、JMockit
* Go：GoLang 1.16
  * Gin、GORM、Go-Resty
  * 測試：Ginkgo、Gomega
* 資料庫：PostgreSQL（GCP CloudSQL）、Redis（由 GKE 自行維運）、MongoDB（由 GKE 自行維運）、Liquibase
* 佇列：RabbitMQ
* CI：GitHub Actions

### SRE
* CI：GitHub CI（Actions）
* SRE：Kubernetes、Kustomize（微服務、Redis、RabbitMQ），由 GKE 提供服務
* 網路：Cloudflare

### 知識管理
* Confluence、JIRA、Trac
* Markdown、AsciiDoc

### 其他
* Bash

## 資深程式設計師（後端）
[Archkite Media](http://www.archkite.com/)<br>
*2019 年 6 月～2020 年 5 月（11 個月）*

負責產品：類似 Airbnb 的線上訂房系統

主要職責：
* 規劃系統架構
* 設計與實作後端服務

### 程式開發
* Java：Java 11、Maven、Jackson JSON
  * 使用 reactive programming（Reactor）
* Spring：Boot、WebFlux、JPA、Cassandra、Redis
* Spring Security：WebFlux Security、Session（Redis）
* 資料庫：PostgreSQL（AWS RDS）、Cassandra、Redis（AWS Elastic Cache）、Liquibase
* 佇列：Kafka
* 測試：JUnit5、AssertJ、JMockit
* CI：GitLab CI、GitHub Actions

### SRE
* SRE：Docker
* AWS：ECS、EC2、VPC、CloudMap、Load Balancer、Route 53
* 網路：Let's Encrypt

### 知識管理
* Trac
* Markdown、AsciiDoc

### 其他
* Bash

## 資深程式設計師（後端）

*香港商翱鶚股份有限公司台灣分公司（Cepave Inc.）台北市（中華民國）*<br>
*2015 年 12 月～2018 年 3 月（2 年 4 個月）*

**公司產品：[OWL](https://github.com/fwtpe/owl-backend)（CDN 分散式監控系統）**

完成事項：
* 指導同事
  * 修正每 5 分鐘執行、耗用 100% MySQL 資源且無法在 5 分鐘內完成的 cron job，使其執行時間縮短為數十秒，且幾乎不影響 MySQL 資源使用。
  * 同時依時間窗（1 分鐘）與資料量（N）進行批次資料寫入，提升寫入吞吐量並降低 MySQL 資料死鎖。
* 設計 DSL，以查詢受監控主機回報的指標。
* 設計並實作 NQM（網路品質管理）服務。
  * 維護並將既有 PHP-NQM 系統移轉至 OWL 系統。
* 簡化微服務架構，將 SQL 集中於單一位置，減輕維運人員工作。

參與項目：
1. Owl-Backend（OWL 核心）：
    * **語言**：Golang、Bash
    * **資料庫**：MySQL
    * **框架／函式庫**：[Beego](https://beego.me/)、[Gin](https://github.com/gin-gonic/gin)、[Gentleman](https://github.com/h2non/gentleman)、[Ginkgo](https://github.com/onsi/ginkgo)
    * **GoLang 工具**：Vendor、GitHub CI、[PEG](https://github.com/pointlander/peg)（GoLang CC）
    * **其他工具**：Maven、Liquibase、YAML、Docker
1. Cassandra API Service（OWL 子系統）：
    * **功能**：NQM（網路品質管理）資料服務
    * **語言**：Java
    * **資料庫**：Cassandra
    * **框架／函式庫**：SpringFramework（Core、Web MVC、Boot）、JMockit、JUnit、TestNG、Java Bean Validation（JSR-380）
    * **其他工具**：Maven、Liquibase、Docker
1. Alert Core 新設計（OWL 子系統）：
    * **語言**：Java
    * **資料庫**：PostgreSQL、Kafka
    * **佇列**：Kafka
    * **框架／函式庫**：SpringFramework（Core、Web MVC、Boot）、JMockit、SLF4j（logback）、JMX、TestNG、JUnit、Java Bean Validation（JSR-380）
    * **其他工具**：Maven、Liquibase、Docker

工程工作：
  1. 後端設計與架構重整。
  1. 資料庫（RDB、Cassandra）設計與效能評估。
  1. [Web MVC 框架](https://godoc.org/github.com/fwtpe/owl-backend/common/gin/mvc)的設計與實作。

改善與指導：
  1. 規劃並導入 RESTful API 慣例。
  1. 規劃並導入自動化測試的程式撰寫規範。
  1. 規劃並導入有狀態服務／模組的自動化測試程式撰寫規範。

## 資深程式設計師（後端）

*博諾資訊（Bonopoints Inc.）台北市（中華民國）*<br>
*2014 年 3 月～2015 年 7 月（1 年 5 個月）*

**公司產品：小型企業的優惠券／會員管理系統（以 RFID 觸發）**

完成事項：
* 建置完整後端服務。
* 據主管所言，我是服務如期交付的關鍵人物。

參與後端系統：
  * **語言**：Java
  * **資料庫**：Google Data Store
  * **雲端服務**：GAE（Google Application Engine）
  * **框架／函式庫**：SpringFramework（Core、Web MVC、Boot）、JPA（JSR-338）、Java Bean Validation（JSR-303）、Shiro、Jersey（JAX-RS）、JUnit、TestNG、JMockit
  * **其他工具**：Maven、Liquibase

工程工作：
  1. 後端設計與架構重整。
  1. 資料庫（RDB）設計與效能評估。

改善與指導：
  1. 規劃並導入 RESTful API 慣例。
  1. 規劃並導入自動化測試（JUnit、TestNG）的程式撰寫規範。
  1. 規劃並導入有狀態程式／模組的自動化測試（JUnit、TestNG）程式撰寫規範。

## 資深程式設計師（後端）

*傳諦股份有限公司（FenzyTV Inc.）台北市（中華民國）*<br>
*2013 年 3 月～2013 年 10 月（8 個月）*

**公司服務：電視節目社群**

完成事項：
* 建置部署流程（Java Web Container、TDD），確保服務上線品質。
* 撰寫 RESTful API 文件。

1. **後端**：Spring Framework（Core、Web MVC）、JPA（JSR-317）、StringTemplate、JAX-RS、Java Bean Validation（JSR-303）、MySQL、Shiro
1. **雲端服務**：RDS、EC2

改善與增強：
  1. 規劃並導入測試框架（JUnit、TestNG）及資料庫演進（Liquibase）。
  1. 規劃 RESTful 服務（JSON）的慣例與規格。

## 資深程式設計師（後端）

*原點科技有限公司（Bluetang Ltd.）台北市（中華民國）*<br>
*2011 年 2 月～2012 年 7 月（1 年 6 個月）*

**公司服務：線上無 schema 資料庫服務（類似 AWS SimpleDB）**

完成事項：
* 建置以時間維度為主的資料倉儲服務。

參與項目：
  1. 網站
      * **Web 技術**：FreeMarker、StringTemplate、HTML、CSS、JavaScript
      * **後端技術**：SpringFramework、JAX-RS、JPA（JSR-317）、Java Bean Validation（JSR-303）、Shiro
      * **資料倉儲／探勘**：PostgreSQL、MySQL
      * **雲端服務**：AWS（RDS、EC2）
  1. Android：行動系統廣告服務的客戶端模組

改善：
  1. 規劃 RDB 資料模型的設計規範。

## 程式設計師

*義美聯合電子商務股份有限公司（I-Mei Multimedia e-Content Production & Marketing Inc.）台北市（中華民國）*<br>
*2010 年 4 月～2011 年 2 月（11 個月）*

**公司：電子書 P2P 平台**

完成事項：
* 透過 TDD，確保整個團隊能產出良好軟體品質。
* 使用 HTTP 函式庫破解 DRM 系統，以實作電子書 DRM（該 DRM 系統沒有 API）。
* 據政府機關人員所言，我們是唯一在系統展示時沒有出錯的公司。

參與項目：
  1. 網站
      1. **Web 技術**：SpringFramework（Web MVC）、FreeMarker、StringTemplate、HTML、CSS、JavaScript
      1. **後端技術**：SpringFramework（Web MVC）、Java Bean Validation（JSR-303）、JPA（JSR-317）、MySQL、PostgreSQL
  1. DRM 整合
      1. 以破解方式（使用 HTTP client）
  1. 導入定義良好的 RDB 資料模型設計原則。
  1. 以 TDD（TestNG）規劃程式撰寫慣例。

## 程式設計師

*肯心資訊股份有限公司（Canthink Inc.）台北市（中華民國）*<br>
*2005 年 2 月～2009 年 12 月（4 年 11 個月）*

**公司產品：E-Learning 系統**

完成事項：
* 據主管所言，嚴謹的資料庫設計方法顯著降低了 bug 數量。
* 找出 ASP engine 記憶體洩漏的原因，使我們能以更簡單的方法更新 script，而無須重啟 IIS。

參與項目：
  1. **核心開發**：ASP（~~.Net~~）、MS SQL Server
  1. **資料庫**：MS SQL Server
  1. **Web**：HTML、JavaScript、CSS、IE 專屬技術

從零開始開發的函式庫／框架：
  1. 日誌函式庫
  1. ORM 框架

-----

# 重要歷程

* *2005～2009*（Canthink Inc.）
  1. 找出 ASP engine 記憶體洩漏的原因。
* *2009～2011*（I-Mei Inc.）
  1. 第一次設計全端系統。
  1. 學習一些編譯器原理。
* *2011～2012*（Bluetang Ltd.）
  1. 第一次使用現代雲端服務。
* *2013*（FanzyTv Inc.）
  1. 體驗到自動化測試的好處。
* *2014～2015*（Bonopoints Inc.）
  1. 我的[主管](https://www.linkedin.com/in/yingfsu/)說，正直是我最可貴的特質。
* *2015～2018*（Cepave Inc.）
  1. 沒有組織職位的情況下，成為其他程式設計師的導師。
  1. 第一次使用 compiler-generator 建置 DSL。
* *2020～2021*（KryptoGo Inc.）
  1. 我的[老闆](https://www.notion.so/b2de72854a8b42609622ce925e328d41)說我像已退休的 NBA 球員 *Tim Duncan*。

我也具備 Perl 與 PHP 程式語言的相關經驗。

-----

# 學歷

龍華科技大學（Lunghwa University of Science and Technology）<br>
資訊管理系（Department of Information Management）<br>
*1999～2003*

維護處實習：
  1. 電腦硬體維護
  1. 網路設定與維護

-----

# 其他

以下為我曾任職且已結束營運的公司。<br>

* *夕煇有限公司（Xihui Inc.）*
* *香港商翱鶚股份有限公司台灣分公司（Cepave Inc.）*
* *博諾資訊（Bonopoints Inc.）*
* *傳諦股份有限公司（FenzyTV Inc.）*
* *原點科技有限公司（Bluetang Ltd.）*
* *肯心資訊股份有限公司（Canthink Inc.）*

