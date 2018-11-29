My Github: [mikelue](https://github.com/mikelue)<br>
My Stackvoerflow: [mikelue](https://stackoverflow.com/users/485957/mike-lue)<br>
My Email Address: [mikelue@ms10.url.com.tw](mikelue@ms10.url.com.tw)<br>

I mainly work for startup company, mostly use AWS services. I have solid experienced with Java programming language and SpringFramework over 10 years.<br>
I am a fundamentalist on **effective automatic testing**.<br>
In recent 3 years, I have learned using CC to build external DSL(Java and GoLang).

The **design of data model**, relational or NoSql databases, is my outstanding skills on implementation of back-end architecture.

-----

**TOC**

* [Work Result](#work-result)
* [Work Experience](#work-experience)
* [Side Projects](#side-projects)
* [Learning History](#learning-history)
* [Education](#education)
* [Good Luck !!](#good-luck-)

-----

# Work result

1. Conventions/Guildlines: [Testing](doc/automatic-testing-conventions.pdf), [RESTful API](doc/common-RESTful-API-conventions.pdf)
    * Examples: [RESTful API example 1](doc/RESTfulAPI-example-1-Complex-Query.pdf)(Complex query), [RESTful API example 2](doc/RESTfulAPI-example-2-CRUD.pdf)(CRUD)
1. Database programming: [Guidelines](doc/guideline-db-code.pdf), [Testing Guidelines](doc/guideline-db-code-testing.pdf)
1. Design of DSL: [Example 1](doc/DSL-example-1.pdf), [Example 2](doc/DSL-example-2.pdf)

-----

# Work Experience

## Senior Programmer

*香港商翱鶚股份有限公司台灣分公司(Cepave Inc.) Taipei City(R.O.C. Taiwan)*<br>
*Dec 2015 ~ Mar 2018(2 years and 4 months)*

**Company Product: [OWL](https://github.com/fwtpe/owl-backend)(Distributed monitoring system for CDN)**

Worked on:

1. Owl-Backend(OWL Core):
    * **Languages**: Golang, Bash
    * **Databases**: MySql
    * **Frameworks/Libraries**: [Beego](https://beego.me/), [Gin](https://github.com/gin-gonic/gin), [Gentleman](https://github.com/h2non/gentleman), [Ginkgo](https://github.com/onsi/ginkgo)
    * **GoLang Tools**: Vendor, Github CI, [PEG](https://github.com/pointlander/peg)(GoLang CC)
    * **Other Tools**: Maven, Liquibase, YAML, Docker
1. Cassandra API Service(OWL subsystem):
    * **Feature**: data service of NQM(Network quality management)
    * **Languages**: Java
    * **Databases**: Cassandra
    * **Frameworks/Libraries**: SpringFramework(Core, Web MVC, Boot), jmockit, JUnit, TestNG, Java Bean Validation(JSR-380)
    * **Other Tools**: Maven, Liquibase, Docker
1. New-Design of alert core(OWL subsystem)
    * **Language**: Java
    * **Databases**: PostgreSql, Kafka
    * **Queueing**: Kafka
    * **Frameworks/Libraries**: SpringFramework(Core, Web MVC, Boot), jmockit, SLF4j(logback), JMX, TestNG, JUnit, Java Bean Validation(JSR-380)
    * **Other Tools**: Maven, Liquibase, Docker

Engineering for:
  1. Back-end design and architecture reforming.
  1. Database(RDB, Cassandra) design and performance evaluation
  1. Design and implementation for [Web MVC framework](https://godoc.org/github.com/fwtpe/owl-backend/common/gin/mvc)

Improvements and Guiding:
  1. Plan and adopt conventions for RESTful API.
  1. Plan and adopt coding guidelines for automatic testing.
  1. Plan and adopt coding guidelines for automatic testing on stateful service/module.

## Senior Programmer

*博諾資訊(Bonopoints Inc.) Taipei City(R.O.C. Taiwan)*<br>
*Mar 2014 ~ Jul 2015(1 year and 5 months)*

**Company Product: coupon/member management for small business(triggered by RFID)**

Worked on back-end system:
  * **Languages**: Java
  * **Databases**: Google Data Store
  * **Cloud services**: GAE(Google Application Engine)
  * **Frameworks/Libraries**: SpringFramework(Core, Web MVC, Boot), JPA(JSR-338), Java Bean Validation(JSR-303), Shiro, Jersey(JAX-RS), JUnit, TestNG, jmockit
  * **Other Tools**: Maven, Liquibase

Engineering for:
  1. Back-end design and architecture reforming.
  1. Database(RDB) design and performance evaluation

Improvements and guiding:
  1. Plan and adopt conventions for RESTful API
  1. Plan and adopt coding guidelines for automatic testing(JUnit, TestNG)
  1. Plan and adopt coding guidelines for automatic testing on stateful program/module(JUnit, TestNG)

## Senior Programmer

*傳諦股份有限公司(FenzyTV Inc.). Taipei City(R.O.C. Taiwan)*<br>
*Mar 2013 ~ Oct 2013(8 months)*

**Company Services: Community for TV Program**

1. **Back-end**: Spring Framework(Core, Web MVC),    JPA(JSR-317),    StringTemplate,    JAX-RS,    Java Bean Validation(JSR-303), MySQL, Shiro
1. **Cloud Services**: RDS,    EC2

Improvements and enhancements:
  1. Plan and adopt on testing framework(JUnit, TestNG) and database evolution(Liquibase)
  1. Plan RESTful services(JSON) conventions and specifications

## Senior Programmer

*原點科技有限公司(Bluetang Ltd.) Taipei City(R.O.C. Taiwan)*<br>
*Fab 2011 ~ Jul 2012(1 year and 6 months)*

**Company Services: Online schemaless-database service(like AWS SimpleDB)**

Worked on:
  1. Web site
      * **Web Tech**: FreeMarker, StringTemplate, HTML, CSS, JavaScript
      * **Backend Tech**: SpringFramework, JAX-RS, JPA(JSR-317), Java Bean Validation(JSR-303), Shiro
      * **Data Warehousing/Mining**: PostgreSQL, MySQL
      * **Cloud Services**: AWS(RDS, EC2)
  1. Android: Client module of advertisement service for mobile system

Improvements:
  1. Plan design disciplines of RDB data model

## Programmer

*義美聯合電子商務股份有限公司(I-Mei Multimedia e-Content Production & Marketing Inc.) Taipei City(R.O.C. Taiwan)*<br>
*Apr 2010 ~ Fab 2011(11 Months)*

**Company: P2P platform of E-Books**

Worked on:
  1. Web site
      1. **Web Tech**: SpringFramework(Web MVC),    FreeMarker,    StringTemplate, HTML, CSS, JavaScript
      1. **Backend Tech**: SpringFramework(Web MVC),    Java Bean Validation(JSR-303), JPA(JSR-317),    MySQL,    PostgreSQL
  1. DRM integration
      1. By hacking approach(with HTTP client)
  1. Adopt well-defined design principals of RDB data model
  1. Plan coding convention by TDD(TestNG)

## Programmer

*肯心資訊股份有限公司(Canthink Inc.) Taipei City(R.O.C. Taiwan)*<br>
*Fab 2005 ~ Dec 2009(4 years and 11 months)*

**Company Product: E-Learning system**

Worked on:
  1. **Core development**: ASP(~~.Net~~), MS SQL Server
  1. **Databases**: MS SQL Server
  1. **Web**: HTML, JavaScript, CSS, IE-specific tech

Development of libraries/frameworks from scratch:
  1. Logging library
  1. ORM framework

-----

# Side projects

[vim-maven-plugin](https://github.com/mikelue/vim-maven-plugin):<br>
A plugin of [VIM](https://www.vim.org/) editor for various convenient usage on Maven execution.

[jdata-unit-test](https://github.com/mikelue/jdata-unit-test):<br>
A plugin(support JUnit and TestNG) to prepare/clean data more easily for (RDB) when running testing on stateful function/program.

-----

# Learning history

* *2005 ~ 2009*(Canthink Inc.)
  1. The basic programming skills and concepts of ORM, IoC(Inverse of Control), logging, and automatic testing
  1. The building of frameworks from scratch(because of [ASP](https://en.wikipedia.org/wiki/Active_Server_Pages)) gives me solid knowledge of how ORM, logging and automatic testing works.
  1. The design of database warehousing/mining.
  1. Thanks to my manager, his open-mind attitude made the system survived the endless challenges for the product(E-Learning system)
  1. In my spare time, I learned the concepts of:
      * memory management of OS
      * how does design of data model impact on databae performance
      * the nature of HTTP
* *2009 ~ 2011*(I-Mei Inc.)
  1. Building for full-stack development(from scratch) of a web system. And development on Java-ecosystem.
    1. JUnit, TestNG for testing
    1. ORM for coding on relational database
    1. Shiro for security of web system
    1. SpringFramework(Core, Web MVC) for well-designed system on implementations.
    1. StringTemplate and Freemarker for front-end.
  1. The usage of [Liquibase](http://www.liquibase.org/) for database evolution.
  1. In my spare time, I learned the concepts of compiler.
* *2011 ~ 2012*(Bluetang Ltd.)
  1. The usage of cloud services(AWS RDS, EC2)
  1. How to formulate the specifications for RESTful API
  1. How to guide the design of database schema for team
  1. Development on Android system
  1. In my spare time, I developed *vim-maven-plugin*
* *2013*(FanzyTv Inc.)
  1. How to guide the development of system with valuable principals.
* *2014 ~ 2015(Bonopoints Inc.)*
  1. The usage of GAE(Goole Application Engine), which is a terrible experience.
  1. Thanks to my manager, let me have confidences in:
      * my design principle of back-end
      * my disciplines of software development.
  1. In my spare time, I developed *jdata-unit-test*
* *2015 ~ 2018*(Cepave Inc.)
  1. The Go programming language, which is not my type of language.
      * The **package(namespace) of module** is a totally disaster of dependency management.
      * The **reflection** is a WTF, compares to Java.
      * The deployment of configuration files for a GoLang program is a nightmare.
      * I am not a child, I don't need the toy of **tag string of struct**.
      * Ecosystem is still an infant.
  1. The first time I design external-DSLs by tools of compiler
  1. Thanks to my colleagues, let me have confidences in:
      * how to adopt my design principle of back-end to the whole team.
      * how to adopt my disciplines of software development to the whole team.
  1. In my spare time, I learned the concepts of:
      * how programing languages turn into assembly language
      * finite-state machine and tuning machine

I also have some experiences on Perl and PHP programming languages.

-----

# Education

龍華科技大學(Lunghwa University of Science and Technology)<br>
資訊管理系(Department of Information Management)<br>
*1999 ~ 2003*

Internship of Maintenance Department:
  1. Maintenance on computer hardware
  1. Network configuration and network maintenance

## Certifications

**Oracle OCA 9i**(2003)

-----

# Good Luck !!

Following list shows the closing down companies for which I worked:<br>
  * *香港商翱鶚股份有限公司台灣分公司(Cepave Inc.)*
  * *博諾資訊(Bonopoints Inc.)*
  * *傳諦股份有限公司(FenzyTV Inc.)*
  * *原點科技有限公司(Bluetang Ltd.)*
  * *肯心資訊股份有限公司(Canthink Inc.)*

Maybe I am still collecting....
