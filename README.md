This is [https://gh.mikelue.guru/](https://gh.mikelue.guru/),
**please visit the site** to gather detail of my career and lastest update.

Check my GitHub: [@mikelue](https://github.com/mikelue), side projects:
* [mikelue/jmisc](https://github.com/mikelue/jmisc) - Some Java utilities/libraries I developed for my work, related to Spring Framework(Core, Data), JPA.
* [mikelue/valor-code](https://github.com/mikelue/valor-code) - Has an imaginary project developed by Spring Framework(Boot, Data/JPA, Data/Cassandra, Message/Kafka) and PostgreSQL/Cassandra/Kafka.
* [mikelue/jdata-unit-test](https://github.com/mikelue/jdata-unit-test) - For self-learning of lambda usage of Java, this project is an imitation of Apache DBUnit.
* [mikelue/go-misc](https://github.com/mikelue/go-misc) - Some GoLang utilities/libraries I developed for my work, related to Ginkgo, Gorm, and a bit of imitation of Spring Framework of Java.
* [mikelue/vim-maven-plugin](https://github.com/mikelue/vim-maven-plugin) - A VIM plugin for Maven.

My Email Address: **[mike.lue0627@msa.hinet.net](mike.lue0627@msa.hinet.net)**<br>

You can check [summary](./Summary.md).

Some documentations I used in my work can be found at [mikelue/mikelue.github.io](https://github.com/mikelue/mikelue.github.io/).

-----

**TOC**

* [Career](#career)
* [Hit History](#hit-history)
* [Education](#education)
* [Else](#else)

# Some experiences I've faced

Software development:
* Software development must have three things, definition, implementation, and testing, whatever developing process you take.
* Most programmers struggle between implementation and testing, rare programmers make good definition.
  * Definition is about make your problem simple, not choose your solution as complex as possible.
  * Implementation is about loyal to specification and deal with the abstraction leaking of IT.
  * Testing is composed of the tests human can do and the ones only computer can do.
* Workaround is always unworthy, unless your don't have to maintain the code anymore(as criminal as I think).

Data design:
* Coding is like starting relationship with someone, data design is like running marriage.
* Lost your code is trivial, lost system data is death sentence.
  * Coding is about correction with sensible algorithms.
  * Data design is about using the least logical I/O to reach your function, whatever you are using SQL or NoSQL databases.
* An algorithm is same however much times you run it.
* A database is not the same one after time passes(like marriage).
* Change code is easy(test, building, restart container), change data is hard(when and how to change).
* When data have bugs, the cost for debugging and fixing is larger than code.

Testing:
* Software quality is like onion, outer layer(front-end) depends on inner layer(back-end).
* The cost to debug in inner layer is larger than in outer layer.
* Unit tests slice the layers for quality insurance.
* You may cost 10x developing time for writing unit testing,
  but you will definitely run the tests more than 10 times.
* The benefits of unit tests
  * Make sure basic quality for next release version (40%)
  * Make sure the upgrading of compiler/libraries on which your software depends is safe (20%)
  * Refactoring existing code without fear(20%)
  * Quickly rule out some suspected problems while your are debugging (20%)

Documentation:
* Writing something for helping yourself to recall the things you might forget in future.
* Writing something for helping others who might take over your code but he or she is unable to contact you directly.
* Something is better than nothing.

# Stuffs affect my design principles

From nowhere:
* *"When specification is lost, all is lost"*
* *"An ounce of prevention is worth a pound of cure."* - *Benjamin Franklin*

From [The Art of SQL, 978-0596008949](https://www.amazon.com/Art-SQL-Stephane-Faroult/dp/0596008945/ref=sr_1_1?keywords=the+art+of+sql&qid=1658546247&s=books&sr=1-1):
* *"Successful data modeling is the disciplined application of what are, fundamentally, simple design principles."*
* *"The sad truth is that when you are beginning to be acknowledged as a skilled SQL tuner, people will not seek your advice until they discover that they have performance problems."*

Other books:
* *"Schema optimization and indexing require a big-picture approach as well as attention to details."* \- [High Performance MySQL](https://www.amazon.com/High-Performance-MySQL-Silvia-Botros-ebook/dp/B09M7W126W/ref=sr_1_1?keywords=High+Performance+MySQL&qid=1658556030&s=books&sr=1-1)

-----

# Career

## Senior Programmer(backend)
*重量科技股份有公司 [KryptoGo Inc.](http://kryptogo.com/)*<br>
*Aug 2020 ~ Aug 2021(1 year)*

Responsible for Product: KYC(Know You Client), CDO(Customer Due Diligence) system

Main responsibilities:
* Take over existing system
* Plan of system architecture
* Design and implement backend service

What I did:
* Build parser to parse juridical verdict to build index for searching.
  * Improve search speed from almost 10 minutes to real time
* Design concurrent web crawling for web page from Google engine
* Simplify architecture(micro-service) of existing system, and that brought decrease in 50% billing(GCP).

### Coding
* Java Stack: Java 13, Maven, Reactor, Jackson JSON
  * Use reactive programming(reactor)
  * Spring Framework Stack: Boot, WebFlux, JPA, Redis
  * Security by Spring Framework: Security over WebFlux, Session(Redis)
  * Testing: JUnit5, AssertJ, Jmockit
* Go Stack: GoLang 1.16
  * Gin, GORM, Go-Resty
  * Testing: Ginkgo, Gomega
* Databases: PostgreSQL(served by GCP CloudSQL), Redis(self-maintaince by GKE), MongoDB(self-maintaince by GKE), Liquibase
* Queuing: RabbitMQ
* CI: Github actions

### SRE
* CI: Github CI(action)
* SRE Stack: Kubernetes, Kustomize(micro-services, redis, RabbitMQ) served by GKE
* Network: Cloudflare

### Knowledge management
* Confluence, JIRA, Trac
* Markdown, AsciiDoc

### Misc
* Bash

## Senior Programmer(backend)
[Archkite Media](http://www.archkite.com/)<br>
*Jun 2019 ~ May 2020(11 months)*

Responsible for Product: Online booking system like airbnb

Main responsibilities:
* Plan of system architecture
* Design and implement backend service

### Coding
* Java Stack: Java 11, Maven, Jackson JSON
  * Use reactive programming(reactor)
* Spring Framework Stack: Boot, WebFlux, JPA, Cassandra, Redis
* Security by Spring Framework: Security over WebFlux, Session(Redis)
* Databases: PostgreSQL(served by AWS RDS), Cassandra, Redis(served by AWS Elastic Cache), Liquibase
* Queuing: Kafka
* Testing: JUnit5, AssertJ, Jmockit
* CI: Gitlab CI, Github actions

### SRE
* SRE Stack: Docker
* AWS Stack: ECS, EC2, VPC, CloudMap, Load Balance, Route 53
* Network: Let's encrypt

### Knowledge management
* Trac
* Markdown, AsciiDoc

### Misc
* Bash

## Senior Programmer(backend)

*香港商翱鶚股份有限公司台灣分公司(Cepave Inc.) Taipei City(R.O.C. Taiwan)*<br>
*Dec 2015 ~ Mar 2018(2 years and 4 months)*

**Company Product: [OWL](https://github.com/fwtpe/owl-backend)(Distributed monitoring system for CDN)**

What I did:

* Mentor colleague
  * To fix a cron job(every 5 minutes), which consumed 100% MySQL resources and could not be finished in 5 minutes,
    as a dozen of seconds runtime and the resource usage of MySQL server was barely noticed.
  * Use both time window(1 minute) and data size(N) to make batch insertion of data, which improved write throughput and decreased data dead lock of MySQL.
* Design a DSL to query metrics reported from monitored hosts.
* Design and implement NQM(network quality management) service.
  * Maintain and transfer from existing PHP-NQM system to OWL system.
* Simplify architecture(micro-service) to make SQL in single place, which eased the work of operators.

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
    * **Databases**: PostgreSQL, Kafka
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

## Senior Programmer(backend)

*博諾資訊(Bonopoints Inc.) Taipei City(R.O.C. Taiwan)*<br>
*Mar 2014 ~ Jul 2015(1 year and 5 months)*

**Company Product: coupon/member management for small business(triggered by RFID)**

What I did:

* Build whole back-end services.
* According my manager, I was the key man for time deliver of service on schedule.

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

## Senior Programmer(backend)

*傳諦股份有限公司(FenzyTV Inc.). Taipei City(R.O.C. Taiwan)*<br>
*Mar 2013 ~ Oct 2013(8 months)*

**Company Services: Community for TV Program**

What I did:

* Build deploy flow(Java Web Container, TDD) to ensure quality of rolling-out service.
* Author documentation of RESTful API

1. **Back-end**: Spring Framework(Core, Web MVC), JPA(JSR-317), StringTemplate, JAX-RS, Java Bean Validation(JSR-303), MySQL, Shiro
1. **Cloud Services**: RDS, EC2

Improvements and enhancements:
  1. Plan and adopt on testing framework(JUnit, TestNG) and database evolution(Liquibase)
  1. Plan RESTful services(JSON) conventions and specifications

## Senior Programmer(backend)

*原點科技有限公司(Bluetang Ltd.) Taipei City(R.O.C. Taiwan)*<br>
*Fab 2011 ~ Jul 2012(1 year and 6 months)*

**Company Services: Online schemaless-database service(like AWS SimpleDB)**

What I did:

* Build data-warehousing service, which was on time-dimension.

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

What I did:

* By TDD, ensured whole team could output fine software quality.
* Use HTTP library to hack DRM system in order to implement DRM for eBooks(the DRM system has no API).
* According to government agent, we were the only one company that there aws no error when demonstrating system.

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

What I did:

* According to my manager, the disciplined method to design database has decreased the number of bugs significantly.
* Figure out the reason of memory leak of ASP engine that we could use a simpler way to update script without rebooting IIS.

Worked on:
  1. **Core development**: ASP(~~.Net~~), MS SQL Server
  1. **Databases**: MS SQL Server
  1. **Web**: HTML, JavaScript, CSS, IE-specific tech

Development of libraries/frameworks from scratch:
  1. Logging library
  1. ORM framework

-----

# Hit history

* *2005 ~ 2009*(Canthink Inc.)
  1. I figured out the reason of memory leak for ASP engine.
* *2009 ~ 2011*(I-Mei Inc.)
  1. First time I designed a full-stack system.
  1. I learned some principal of compiler.
* *2011 ~ 2012*(Bluetang Ltd.)
  1. First time I used modern cloud services.
* *2013*(FanzyTv Inc.)
  1. I experienced benefits of automatic tests.
* *2014 ~ 2015*(Bonopoints Inc.)
  1. My [manager](https://www.linkedin.com/in/yingfsu/) said that my integrity is the most valuable characteristic of me.
* *2015 ~ 2018*(Cepave Inc.)
  1. I became mentor of other programmers without organization position.
  1. First time I used compiler-generator to build DSL.
* *2020 ~ 2021*(KryptoGo Inc.)
  1. My [boss](https://www.notion.so/b2de72854a8b42609622ce925e328d41) said that I like the *Tim Duncan*, who is retired player of NBA.

I also have some experiences on Perl and PHP programming languages.

-----

# Education

龍華科技大學(Lunghwa University of Science and Technology)<br>
資訊管理系(Department of Information Management)<br>
*1999 ~ 2003*

Internship of Maintenance Department:
  1. Maintenance on computer hardware
  1. Network configuration and network maintenance

-----

# Else

Following list are the closed down companies I had worked for.<br>

* *香港商翱鶚股份有限公司台灣分公司(Cepave Inc.)*
* *博諾資訊(Bonopoints Inc.)*
* *傳諦股份有限公司(FenzyTV Inc.)*
* *原點科技有限公司(Bluetang Ltd.)*
* *肯心資訊股份有限公司(Canthink Inc.)*
