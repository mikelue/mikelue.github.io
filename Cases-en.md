## Table of Contents

- [Additional Question](#additional-question)
- [CI/CD](#cicd)
- [Spring Framework](#spring-framework)
- [Service Failure](#service-failure)
- [Foundation of professional knowledge](#foundation-of-professional-knowledge)
- [Unit Test](#unit-test)
- [Java Heap Analysis](#java-heap-analysis)
- [Complex Configuration](#complex-configuration)
- [Parser](#parser)
- [Web MVC](#web-mvc)
- [Database Optimization](#database-optimization)
- [Web Scraper](#web-scraper)
- [Internal Fragmentation](#internal-fragmentation)

## Additional Question

* Background: lottery system
    * Java, Spring Framework
* Scenario:
    * Discussed a feature that failed stress testing during a meeting.
    * Decided to disable a specific feature first to confirm it was the bottleneck.
* How the issue was discovered:
    * I had read the relevant code beforehand.
    * QA suggested disabling the feature from the UI first.
    * Based on my understanding of the implementation, I realized it did not account for the feature being disabled.
    * QA confirmed that disabling it had not been implemented and would impose withdrawal restrictions.
* Takeaway: In the AI era, reading code may seem inefficient, but understanding a system can reveal new bugs in other contexts.

## CI/CD

* Background: lottery system
    * Self-hosted GitLab
    * Self-hosted Maven Nexus
* Problem:
    * Deploying six microservices to the development environment took ten minutes.
* Other side effects:
    * DevOps found that Nexus capacity was saturated, preventing builds across the company.
        * Two Nexus instances were set up and assigned to separate teams.
    * With each engineer updating an average of six times per day, about one hour was spent waiting for CI/CD.
* Resolution:
    * During gaps between my own tasks, I investigated the cause and found two issues:
        1. The Maven repository cache in GitLab CI/CD was configured incorrectly, so dependencies were downloaded again for every build.
        1. The same `mvn compile` command was executed twice.
    * Adjusted the pipeline to operate properly.
    * Deployment completed in two and a half minutes.
* Takeaway: Seemingly minor issues can impose costs on teams and other departments.

## Spring Framework

* Background: lottery system
    * Used _MyBatis-Flex_ as the ORM.
* Problem:
    * A colleague found an integration issue with Spring Framework's `@Transactional`.
    * While developing database unit tests with `DataJpaTest`, I also found that transactions were not rolled back automatically.
* Resolution:
    * I reviewed the MyBatis-Flex source code and found that it wrapped the default _Data Source_ with its own _Data Source_, causing inconsistent `@Transactional` behavior.
    * Configured the MyBatis-Flex _Data Source_ as the default data source in the Spring context.
* Follow-up:
    * A stress test with 100,000 orders failed before the change and passed afterwards.
* Takeaway:
    * Application infrastructure has a broad impact; framework behavior must match expectations.

## Service Failure

* Background: cryptocurrency exchange
    * Java, Spring Framework
* Problem:
    * DevOps found that HTTP requests in production could sometimes not be handled, with no clear error message.
    * The system remained operational, making the behavior appear random.
* Investigation:
    * HTTP logs only showed 5xx responses without further information.
    * The microservice logs contained no errors and appeared not to have received the failing HTTP requests.
    * Worked with DevOps to inspect the nginx logs.
    * Found a `ulimit` "too many open files" error.
* Takeaway: Troubleshooting requires considering the entire system and breaking the problem down step by step.

## Foundation of professional knowledge

* Background: Cryptocurrency exchange
  * Java, Spring Framework
* Problem:
  * A microservice developed by colleague A could not process market data quickly enough for database storage, even on a 16-core VM, according to the DevOps team.
  * While colleague B continued developing features for the module, they discovered many issues involving missing data.
* Cause:
  * After receiving each batch of market data, the module created a new Java `Executor` and then shut it down.
* Solution:
  * Recommended that colleague B revise the multithreading strategy and change the implementation to write data to the database using batches from a buffered queue.
* Result:
  * The VM was reduced to four cores, while the microservice’s average CPU usage became approximately 20%.
* Takeaway:
  A solid understanding of multithreading practices and high-volume database writes is extremely important.

## Unit Test

* Background: cryptocurrency exchange
    * Java, Spring Framework
* Problem:
    * After a vulnerability scan, colleague A replaced an encryption function.
        * The function returned a *Base64* string.
    * Only a few functions were tested.
    * After deployment, deposits and withdrawals failed.
* Cause: The new function returned letters with different casing, and colleague A happened to test only functionality using `equalsIgnoreCase()`.
* My approach:
    * Shortly before this, I had refactored another similar feature.
    * I used TDD and wrote tests first.
* Follow-up:
    * In a retrospective meeting, I shared my approach for ensuring existing behavior remained correct.
    * I also explained that encrypted content can be verified by comparing the binary data directly, avoiding string-case issues.
* Takeaway:
    * Simple unit tests can ensure the correctness of critical system functionality.

## Java Heap Analysis

* Background: cryptocurrency exchange
    * Java, Spring Framework
* Problem:
    * A feature developed by colleague A repeatedly caused a Java microservice to shut down.
* Investigation:
    * After checking the messages, I found a heap out-of-memory error.
    * After dumping the JVM heap and examining it with VisualVM, I found that this Hibernate version generated an abstract syntax tree (AST) for every distinct number of values in `WHERE prop IN (?)`, causing memory usage to increase gradually with system load.

## Complex Configuration

* Background: cryptocurrency exchange
    * Java, Spring Framework
* Task: Prepare to migrate JVM microservices, currently deployed manually on VMs, to Kubernetes.
* Problem:
    * Backend developers supplied the configuration, and the tech lead compared Git files to identify configuration changes.
    * DevOps then applied the required configuration updates.
    * Human errors occurred frequently.
* Resolution:
    * Separated environment-dependent and environment-independent configuration, simplifying the configuration actually required for deployment.
    * Reduced the number of deployment configuration items from 40–50 to 4–10.
* Follow-up: Due to other circumstances, DevOps did not have time to proceed with the Kubernetes migration.
* Benefit: Existing deployments became simpler for DevOps and were no longer as prone to human error.

## Parser

* Background: KYC system
* Problem:
    * Court judgments were converted from entire PDFs into a single JSON property, with lines separated by newline characters.
    * Multiple official-document formats had to be supported.
    * The original asynchronous query process searched through 40 GB of full JSON text for every query.
    * Operating costs were too high.
* Resolution:
    * Developed a two-phase parser to create the indexes required for KYC.

## Web MVC

* Background: CDN monitoring system
    * Go, MySQL
    * Used _gin_ as the framework.
* Motivation: To simplify development, I modeled a declarative _gin_ extension mechanism after Spring Web MVC.
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
* Takeaway: Many Spring Framework design principles are worth drawing from.

## Database Optimization

* Background: CDN monitoring system
    * Go, MySQL
    * A reporting feature written by colleague A caused extensive MySQL deadlocks and locked up the entire system.
    * Colleague B was assigned to fix the feature.
* Problem:
    * It loaded all data into the microservice for calculation.
    * It created a new goroutine for every record written to execute an `INSERT`.
* Process:
    * Colleague B asked for my help.
    * I suggested avoiding loading all data from the database for calculation; instead, create appropriate indexes and generate data in batches.
    * For continuously arriving monitoring data, I suggested storing it in MySQL through a buffered/interval-based dual-track approach.
* Result: The feature operated correctly and reduced the original load to 30%.
* Takeaway: Database design needs thorough up-front planning; later problems and modification costs are too high.

## Web Scraper

* Year: 2010
* Background: E-book system integrated with DRM
    * The DRM was a web UI system without an API.
* Technology: Java, Spring Framework
    * Developed a web scraper with Apache HTTP Client to simulate login, creation, and retrieval of DRM information.
* Takeaway:
    * Understanding how HTTP works is the last resort for integrating with legacy web systems.

## Internal Fragmentation

* Background: E-learning system (my first job)
* Technology: First-generation Microsoft ASP (VBScript)/IIS, a dynamic scripting language
* Problem:
    * The company developed a tool that uploaded partial file updates to update the system without restarting IIS.
    * An out-of-memory error occasionally occurred and required restarting IIS.
    * Windows system monitoring showed sufficient available memory.
* Resolution:
    * I reread the memory-management chapter of *Operating System Principles*.
    * Internal fragmentation gave me an idea.
    * Fortunately, every page in the system included a `common.asp` file.
    * Every update was forced to include an update to `common.asp`.
    * After practical testing, the out-of-memory error no longer occurred.
* Takeaway: Computer science fundamentals always provide help at the deepest level.
