# Spring Boot FAQ

## What is Spring Boot?

Spring Boot is an open-source Java-based framework designed to simplify the development of Spring applications by providing a convention-over-configuration approach and ready-to-use modules.

## What are the important Goals of Spring Boot?

1. Provide a rapid development environment.
2. Offer opinionated defaults to minimize configuration.
3. Promote good development practices.
4. Minimize boilerplate code and configuration.

## What are the important Features of Spring Boot?

- **Auto-configuration:** Automatically configures Spring applications based on dependencies.
- **Starter Projects:** Pre-configured dependencies for various use cases.
- **Embedded Servers:** Simplifies deployment by including embedded HTTP servers.
- **Production-ready features:** Includes monitoring, health checks, and externalized configuration.

## Compare Spring Boot vs Spring.

- **Spring:** Comprehensive framework requiring explicit configuration.
- **Spring Boot:** Simplifies Spring development with convention-over-configuration and auto-configuration.

## Compare Spring Boot vs Spring MVC.

- **Spring MVC:** Part of Spring framework focused on building web applications.
- **Spring Boot:** Incorporates Spring MVC with added features for rapid development and deployment.

## What is the importance of `@SpringBootApplication`?

- Marks the main class of a Spring Boot application.
- Enables auto-configuration and component scanning.

## What is Auto Configuration?

Automatically configures Spring applications based on classpath settings, dependencies, and other factors.

## How can we find more information about Auto Configuration?

Refer to the official Spring Boot documentation or source code for detailed information on how auto-configuration works.

## What is an embedded server? Why is it important?

An embedded server is an HTTP server bundled within the application, simplifying deployment by eliminating the need for external server setups.

## What is the default embedded server with Spring Boot?

Apache Tomcat is the default embedded server with Spring Boot.

## What are the other embedded servers supported by Spring Boot?

Jetty and Undertow are other embedded servers supported by Spring Boot.

## What are Starter Projects?

Starter Projects are pre-configured dependencies for specific functionalities or use cases.

## Can you give examples of important starter projects?

Examples include `spring-boot-starter-web` for web applications and `spring-boot-starter-data-jpa` for JPA data access.

## What is Starter Parent?

Starter Parent is a parent POM that defines common configurations for Spring Boot projects.

## What are the different things that are defined in Starter Parent?

Dependency management, plugin configuration, and default properties are defined in Starter Parent.

## How does Spring Boot enforce common dependency management for all its Starter projects?

Spring Boot uses the Starter Parent POM to enforce common dependency versions across all Starter projects.

## What is Spring Initializr?

Spring Initializr is a web-based tool to generate Spring Boot projects with required dependencies.

## What is `application.properties`?

`application.properties` is a configuration file for Spring Boot applications, containing key-value pairs to customize application behavior.

## What are some of the important things that can be customized in `application.properties`?

Logging levels, database connections, and server ports are some important configurations that can be customized in `application.properties`.

## How do you externalize configuration using Spring Boot?

Configuration can be externalized by storing properties in external files or environment variables.

## How can you add custom application properties using Spring Boot?

Custom properties can be added to `application.properties` or YAML files.

## What is `@ConfigurationProperties`?

`@ConfigurationProperties` maps external configuration properties to Java objects.

## What is a profile?

A profile is a way to segregate application configuration based on environments like development, testing, and production.

## How do you define beans for a specific profile?

Use the `@Profile` annotation on bean definition methods.

## How do you create application configuration for a specific profile?

Create separate configuration files suffixed with profile names (e.g., `application-dev.properties`).

## How do you have different configuration for different environments?

Use Spring profiles to manage configurations for different environments.

## What is Spring Boot Actuator?

Spring Boot Actuator provides production-ready features for monitoring and managing Spring Boot applications.

## How do you monitor web services using Spring Boot Actuator?

Spring Boot Actuator endpoints provide information about application health, metrics, and more, which can be accessed to monitor web services.

## How do you find more information about your application environment using Spring Boot?

Spring Boot Actuator endpoints like `/env` and `/info` provide information about the application environment.

## What is a CommandLineRunner?

CommandLineRunner is an interface in Spring Boot used to execute code after the application context is loaded, primarily for tasks like data initialization.

## What Is Spring JdbcTemplate Class and How to Use It?

Spring JdbcTemplate is a part of the Spring JDBC module used to simplify the interaction with JDBC APIs. It abstracts away the boilerplate code required for database operations. You can use it by injecting a JdbcTemplate instance into your Spring-managed beans and then using its methods to perform database operations.

## How Would You Enable Transactions in Spring and What Are Their Benefits?

Transactions in Spring can be enabled either programmatically using `@Transactional` annotation or declaratively using XML or Java configuration. Benefits of transactions include data integrity, consistency, and isolation, ensuring that a group of operations either all succeed or all fail.

## What Is Spring Dao?

In Spring, DAO (Data Access Object) is an object responsible for performing CRUD (Create, Read, Update, Delete) operations on the database. It abstracts away the database-specific details and provides a clean interface for the application to interact with the database.

## What is Spring Data?

Spring Data is a part of the Spring ecosystem that provides a consistent and easy way to work with different data access technologies, including relational databases, NoSQL databases, and more.

## What is the need for Spring Data?

Spring Data simplifies the data access layer by providing a unified and consistent programming model for different data stores. It reduces boilerplate code and improves productivity by automating common data access tasks.

## What is Spring Data JPA?

Spring Data JPA is a sub-project of Spring Data that provides support for JPA (Java Persistence API) based data access in Spring applications. It simplifies the implementation of data access layer by providing repository interfaces that automatically generate database queries based on method names.

## What is a CrudRepository?

CrudRepository is a Spring Data interface that provides CRUD (Create, Read, Update, Delete) operations on the underlying data source. It is a generic interface that can be extended to create repositories for specific domain entities.

## What is a PagingAndSortingRepository?

PagingAndSortingRepository is a sub-interface of CrudRepository in Spring Data that provides additional methods for pagination and sorting of query results.

## What Is Aspect-Oriented Programming?

Aspect-Oriented Programming (AOP) is a programming paradigm that allows modularization of cross-cutting concerns (e.g., logging, transaction management) from the core business logic of an application.

## What Are Aspect, Advice, Pointcut, and Joinpoint in Aop?

- **Aspect:** A module encapsulating cross-cutting concerns.
- **Advice:** The action taken by an aspect at a particular join point.
- **Pointcut:** A predicate that matches join points where advice should be applied.
- **Joinpoint:** A point during the execution of a program, such as method execution or exception handling.

## What Is Weaving?

Weaving is the process of integrating aspects with the core application code at specified join points during the program execution lifecycle.

## What are cross-cutting concerns?

Cross-cutting concerns are aspects of a program that affect multiple modules and are not localized to a specific module or layer.

## How do you implement cross-cutting concerns in a web application?

Cross-cutting concerns can be implemented using AOP, where aspects are used to encapsulate common functionalities like logging, security, and transaction management.

## If you would want to log every request to a web application, what are the options you can think of?

1. Use Spring AOP to create an aspect that intercepts requests and logs relevant information.
2. Use Spring Boot's built-in support for request logging.

## If you would want to track performance of every request, what options can you think of?

1. Implement a custom interceptor or filter to measure request processing time.
2. Use Spring Boot Actuator to monitor application performance metrics.

## What is an Aspect and Pointcut in AOP?

- **Aspect:** A module encapsulating cross-cutting concerns.
- **Pointcut:** A predicate that matches join points where advice should be applied.

## What are the different types of AOP advices?

The different types of AOP advices are:
- Before advice: Executed before the advised method.
- After returning advice: Executed after the advised method returns a value.
- After throwing advice: Executed if the advised method throws an exception.
- After (finally) advice: Executed after the advised method completes, regardless of its outcome.
- Around advice: Wraps the advised method, allowing for custom behavior before and after its invocation.

## What is weaving?

Weaving is the process of integrating aspects with the core application code at specified join points during the program execution lifecycle.

## Compare Spring AOP vs AspectJ?

- **Spring AOP:** AOP framework provided by Spring, using proxy-based approach and limited to Spring-managed beans.
- **AspectJ:** A more comprehensive AOP framework that offers more powerful features like load-time weaving and compile-time weaving, and can be used with any Java class.

## What Is Reactive Programming?

Reactive programming is a programming paradigm focused on asynchronous data streams and the propagation of changes.

## What Is Spring Webflux?

Spring Webflux is a reactive web framework provided by Spring for building non-blocking, asynchronous, and event-driven applications.

## What Are the Mono and Flux Types?

- **Mono:** Represents a stream emitting at most one element, useful for handling asynchronous operations with a single result.
- **Flux:** Represents a stream emitting zero to many elements, useful for handling asynchronous operations with multiple results.

## What Is the Use of WebClient and WebTestClient?

- **WebClient:** A non-blocking, reactive HTTP client provided by Spring Webflux for making HTTP requests.
- **WebTestClient:** A testing utility provided by Spring Webflux for testing reactive web applications.

## What Are the Disadvantages of Using Reactive Streams?

- Steeper learning curve compared to traditional imperative programming.
- Debugging asynchronous code can be challenging.
- Overhead of dealing with backpressure in reactive streams.

## Is Spring 5 Compatible with Older Versions of Java?

Spring 5 is compatible with Java 8 and higher versions.

## How Does Spring 5 Integrate with Jdk 9 Modularity?

Spring 5 provides compatibility with Java 9 modules, allowing Spring-based applications to run on Java 9+ runtime environments.

## Can We Use Both Web Mvc and Webflux in the Same Application?

Yes, it is possible to use both Spring Web MVC and Spring Webflux in the same application, allowing developers to choose between blocking and non-blocking approaches based on their requirements.



## Project Author
Akash Shinge