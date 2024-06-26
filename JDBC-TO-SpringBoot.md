# Database Driver

A database driver is a software component that enables a Java application to interact with a database. It acts as a bridge between the application and the database, facilitating communication. There are four different types of database drivers:

## Type I (JDBC-ODBC Bridge Driver):
- Connects Java applications to databases using JDBC (Java Database Connectivity) and ODBC (Open Database Connectivity).
- Initially supported in Java but removed in Java 7 due to ODBC being specific to Windows.

## Type II (JDBC Native API Driver):
- Avoids the use of ODBC and relies on vendor-specific drivers.
- Removes OS dependency, but the vendor-specific driver needs to be installed on each system.
- Examples include the Oracle OCI driver (now outdated).

## Type III (JDBC Network Protocol Driver):
- Utilizes a middleware server to transform API calls from clients to the server.
- The server sends a small copy of the API to the client machine over the internet.
- Also known as the middleware driver, with examples like WebLogic RMI driver.

## Type IV (JDBC Thin/Universal Driver):
- Does not require a middleware driver to connect to the database.
- Facilitates a two-step process: Java code connects to the database using Type IV, and then Type IV interacts with the database.
- Fully written in Java, portable, and supports vendor-specific implementations.
- Examples include MySQL Connector and Oracle thin driver.

### JDBC Objects:

#### Driver:
- Establishes a socket connection with the database and handles authentication.
- Needs to be registered with the DriverManager.
- Manages a set of JDBC drivers for different databases.

#### Connection:
- Encapsulates the socket connection and is used for creating statements and managing transactions.

#### Statement:
 - Statement is an interface that present in java.sql.* package
 - Its main purpose to represents SQL Statement & execute query with the database.
 - It compiled & execute every time for each query
 - It is used to execute different type of query like create,update,select & delete etc 
 - It contains different methods like execute(),executeQuery(),executeUpdate().
 - Each methods has its own functionality 
 - execute() methods used to perform DDL oeprations like create,drop,and truncate the table & it returns only boolean value either true or false to validate table status changes.
 - executeQuery() methods used to perform DQL oeprations like select table data & it returns ResultSet Object, with the help of ResultSet Object we can get data from database
 - executeUpdate() methods used to perform DML oeprations like insert, delete & update & it returns a interger value. That meaning is row is upadated successfully

 #### preparedStatement:

- PreparedStatement is an interface that present in java.sql.* package
 - PreparedStatement is a subclass of Statement, it can do what a Statement can do, plus more
 - PreparedStatement Object represents a precompiled SQL statement. Means When PreparedStatement is created, the SQL query is passed as a parameter. This Prepared Statement contains a pre-compiled SQL query, so you can be be used to execute the statement multiple times.
 - we use prepareStatement() method of the Connection interface. This method accepts a query (parameterized) and returns a PreparedStatement object.so it works both static and dynamic queries.
 - If we use dynamic queries for prepareStatement() method then we can set parameter value by setter method of PreparedStatement.
 - PreparedStatement is best choice because it escapes the special characters  from query and avoid SQL injection attacks.

#### ResultSet:
- Acts like a cursor in databases, allowing access to rows of records one by one.

### MySQL and Oracle Driver Connections:

**MySQL Driver Connection:**

String DB_DRIVER = "com.mysql.cj.jdbc.Driver";
String DB_URL = "jdbc:mysql://localhost:3306/emp161db";
String DB_USER = "root";
String DB_PASSWORD = "Akash@123";




# Difference Between Statement & PreparedStatement:

## Statement:
- Associated with multiple queries at once.
- Compiles and executes each time.
- Works only with static queries.
- Relatively lower performance.
- Suitable for scenarios with multiple queries but prone to SQL injection attacks.

## PreparedStatement:
- Associated with only one query.
- Compiles once, executes multiple times.
- Supports both static and dynamic queries.
- Higher performance.
- Ideal for scenarios with a single query and parameterized inputs, preventing SQL injection attacks.

# HTTP Protocol:

HTTP (Hypertext Transfer Protocol) is a set of rules governing the communication between web browsers and servers. It is stateless, meaning the connection between browser and server is lost after each transaction.

# HTTP Request & HTTP Response:

HTTP follows the Request-Response model, where an HTTP request is made by the client to the server, and the server responds accordingly. An HTTP request consists of request headers and an optional request body.

# HTTP Methods:

1. GET: Fetches data from the backend server.
2. POST: Sends data from the frontend server to the backend server.
3. PUT: Updates a particular record.
4. DELETE: Deletes a particular record.

# Servlet

A Servlet is a server-side technology used to handle client (browser) requests, process them, and generate dynamic responses. It operates within a web container, such as Apache Tomcat. Servlets can be used to create dynamic web pages, process form data, and interact with databases.

# Servlet Life Cycle:

1. init: Invoked only once during servlet initialization.
2. service: Handles client requests, often invoking the doGet, doPost, etc., methods.
3. destroy: Invoked when the servlet is being removed from service.

# Request Dispatcher:

A Request Dispatcher is an interface used for servlet collaboration, allowing one servlet to forward requests to another servlet or include content from another source (like an HTML file). It has methods forward(request, response) and include(request, response) to handle dispatching. When forwarding requests, the URL remains unchanged.

# Forward & Include:

- Forward: Completely forwards the request to another servlet without returning to the original servlet. The URL remains unchanged.
- Include: Includes content from another source (like an HTML file) in the response. The URL remains unchanged.

# Session Management:

Servlets can manage sessions to maintain user state across multiple requests. Sessions can store user-specific data, allowing servlets to identify users and track their interactions.

# Difference Between Hibernate & JDBC:

## Hibernate:
- Java-based ORM (Object-Relational Mapping) framework.
- Maps entity class objects directly to the database using predefined annotations.
- Manages exceptions internally.
- Supports HQL (Hibernate Query Language) for additional features like inheritance and associations.
- Provides easy management of associations like one-to-one, one-to-many, etc.
- Offers good support for lazy loading.
- Handles transaction management automatically.
- Provides two-level caching mechanisms (L1 and L2 cache).

## JDBC:
- Database connectivity tool for Java.
- Does not directly map entity class objects to the database; requires manual coding.
- Developers need to handle exceptions using try-catch blocks.
- Executes SQL queries using structured query language.
- Difficult to manage associations.

# What is JPA?

- JPA (Java Persistence API) is an ORM (Object-Relational Mapping) framework that provides a bridge for communication between your application (Java/Python/.NET) and a relational database.
- It simplifies database interactions by mapping Java objects to database tables and vice versa.
- Popular JPA providers include Hibernate, TopLink, MyBatis, and EclipseLink, each with its own API methods for database interaction.
- JPA defines a set of specifications or rules for ORM frameworks in Java.
- It offers interfaces and methods for common operations like saving and updating data, which can be implemented by any ORM provider.
- JPA standardizes ORM practices across different providers, making it easier to switch between them without significant code changes.

# Difference Between Hibernate & JDBC

## Hibernate

- Hibernate is a Java-based ORM framework.
- It maps entity class objects directly to the database using predefined annotations.
- Hibernate manages exceptions internally.
- It uses HQL (Hibernate Query Language) similar to SQL to provide additional features of OOPS concepts like inheritance and associations.
- Hibernate supports various types of associations like one-to-one, one-to-many, many-to-one, and many-to-many using annotations.
- Hibernate provides good support for lazy loading.
- Transaction management is handled automatically by Hibernate.
- It provides two-level caching mechanisms (L1 and L2 cache).

## JDBC

- JDBC (Java Database Connectivity) is a database connectivity tool for Java.
- It does not directly map entity class objects to the database; manual coding is required.
- Developers need to handle exceptions using try-catch blocks.
- JDBC executes SQL queries using structured query language.
- It is difficult to manage associations like one-to-one, many-to-one, etc., in JDBC.
- JDBC does not support lazy loading.
- Transaction management is managed by JDBC itself when working with JDBC code.
- JDBC has a strong community for getting solutions to issues, providing good support services.
- JDBC requires writing code for implementing caching.

# What is Maven?

- Maven is a project management and build automation tool.
- It manages dependencies, compiles the project, runs tests, packages the project for deployment, and generates reports.
- The name "Maven" means "Accumulator of knowledge" in Yiddish.
- Maven is developed by the Apache Software Foundation.
- It uses a Project Object Model (POM) for project configuration, specifying project details like Java version, Spring version, dependencies, packaging format, etc.
- Maven builds projects into desired output formats like .jar or .war.
- It is widely used for Java-based projects and is written in Java.
- Maven defines build lifecycles and phases, such as validate, compile, test, package, install, and deploy, to manage project tasks efficiently.

# How Maven Works

- Maven works by following a project structure that includes source code, test code, resources, dependencies/libraries, configuration, and task runners for build, test, and run operations.
- It uses the Project Object Model (POM) to define project configurations, dependencies, and build settings.
- Maven builds projects by executing lifecycle phases like validate, compile, test, package, install, and deploy, as specified in the POM.
- It manages dependencies and downloads required libraries from repositories specified in the POM.
- Maven provides reports and feedback on project build and test results.

# What is Spring?

- Spring is a comprehensive framework for simplifying Java (SE+EE) development.
- It is lightweight, flexible, and modular, providing various functionalities for building enterprise applications.
- Spring simplifies Java development by allowing developers to focus on business logic while managing testing, integration, and other tasks.
- The core feature of Spring is Inversion of Control (IoC) and Dependency Injection (DI), which promote loose coupling and easy integration.
- Spring offers various modules for different functionalities like data access, transaction management, web development, etc.
- It follows a modular architecture, allowing developers to choose components based on project requirements.

# What is IoC (Inversion of Control)?

- IoC (Inversion of Control) is an architectural pattern that describes how dependencies are managed in a system.
- In IoC, the control of object creation and dependency injection is shifted from the application to an external entity (usually a framework or container).
- It eliminates tight coupling between components and promotes loose coupling, making the system more flexible and easier to maintain.
- IoC is achieved through Dependency Injection (DI), where the dependencies of a component are injected into it rather than created by the component itself.
- Spring IoC container is responsible for managing object creation, lifecycle, and dependency injection in Spring applications.

## IoC Container Types:

1. **BeanFactory**: Interface for accessing beans defined in the Spring container.
2. **ApplicationContext**: Interface that extends BeanFactory and provides additional features like event handling, internationalization, etc.
   - Application Context is the primary Spring container used for developing enterprise applications.
   - Commonly used implementation class: `ClassPathXmlApplicationContext`.

# Annotation Based Configuration

- Spring supports annotation-based configuration, allowing developers to define beans, dependencies, and other configurations using annotations.
- Annotations like `@Bean`, `@Component`, `@Autowired`, etc., are used for defining beans, component scanning, and dependency injection.
- `@Bean` annotation is used to define a bean method within a configuration class, typically used for creating beans of third-party classes.
- `@Component` annotation is a stereotype annotation used to mark a class as a component, typically used for defining beans of user-defined classes.
- Both `@Bean` and `@Component` provide ways to register beans in the Spring IoC container, with slight differences in usage and preferences.

## @Bean vs @Component

### @Bean

- Defines a bean method within a configuration class.
- Typically used for creating beans of third-party classes.
- Allows customization of bean creation and behavior.
- Can have arguments to inject dependencies into the bean instance.
- Preferable for wiring components from third-party libraries.

### @Component

- Marks a class as a component, typically a user-defined class.
- Provides a convenient way to register a class as a bean without separate configuration.
- Typically used for simple initialization processes.
- Relies on component scanning and automatic wiring.
- Preferable for component scanning and automatic wiring.

## @Autowired

- `@Autowired` is used for Dependency Injection (DI) in Spring applications.
- It injects dependencies into beans automatically, eliminating the need for manual bean creation and wiring.
- `@Autowired` can be applied at the field level, setter method, or constructor to inject dependencies.

