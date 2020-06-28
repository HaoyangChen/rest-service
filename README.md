# SpringBootLearning

## Task1: Learning
### 1: Compare the three popular Java frameworks and describe the difference

|Factors | Spring Boot | DropWizard | Play |
| --- | --- | --- | --- |
| What is it? |Takes an opinionated view of building production-ready Spring applications. Spring Boot favours convention over configuration and is designed to get you up and running as quickly as possible.|Dropwizard pulls together stable, mature libraries from the Java ecosystem into a simple, light-weight package that lets you focus on getting things done|Play is a high-productivity Java and Scala web application framework that integrates components and APIs for modern web application development.|
|Dependency Injection? | Built in Dependency Injection provided by Spring Dependency Injection container |  No built in Dependency Injection. Requires a 3rd party dependency injection framework such as Guice, CDI or Dagger | Play does not use any dependency injection framework under the hood; Play provides dependency injection support based on JSR 330. The default JSR 330 implementation that comes with Play is Guice, but other JSR 330 implementations can be plugged in.|
|Libraries|Spring, JUnit, Logback, Guava. There are several starter POM files covering various use cases, which can be included in the POM to get started |	 Core: Jetty, Jersey, Jackson and Matrics; Others: Guava, Liquibase and Joda Time.| Scala |


### 2: Gradle and Maven difference
|Factors | Gradle | Maven |
|---|---|---|
|What is it?| Gradle is a build automation system that is fully open source and uses the concepts you see on Apache Maven and Apache Ant. It uses domain-specific language based on the programming language Groovy, differentiating it from Apache Maven, which uses XML for its project configuration. It also determines the order of tasks run by using a directed acyclic graph.| Maven is used for project build automation using Java. It helps you map out how a particular software is built, as well as its different dependencies. It uses an XML file to describe the project that you are building, the dependencies of the software with regards to third-party modules and parts, the build order, as well as the needed plugins. There are pre-defined targets for tasks such as packaging and compiling. |
| Flexibility | Gradle is built with an empowered and responsible user in mind| Maven provides a very rigid model that makes customization tedious and sometimes impossible |
| Performance | Employ some form of parallel project building and parallel dependency resolution. Its features of incrementality, build cache, and gradle daemon make Gradle much faster than Maven |Employ some form of parallel project building and parallel dependency resolution. |
| Dependency Management | Provides customizable dependency selection and substitution rules that can be declared once and handle unwanted dependencies project-wide. Allows custom dependency scopes, which provides better-modeled and faster builds. | allows one to override a dependency, but only by version; Few, built-in dependency scopes|

### 3: Docker
Docker is a set of platform as a service products that uses OS-level virtualization to deliver software in packages called containers. It is a Linux container management toolkit with a "social" aspect, allowing users to publish container images and consume those published by others. Containers are isolated from one another and bundle their own software, libraries and configuration files; they can communicate with each other through well-defined channels.


## Task 2: Init/build a simple microservice application using Spring Boot framework
To view the RESTful Web Service, you can run this command 
`./mvnw spring-boot:run` to run the application and visit `http://localhost:8080/greeting` or `http://localhost:8080/greeting?name=User`

## Task 3: Running the service in Docker

Prerequisites: Downloaded and installed the VirtualBox and Docker

Windows 10 Home User? See [Configure Docker for Windows 10 Home](https://juejin.im/post/5e158594f265da5d0c5428dc)

Step 1: Created Dockerfile at the Root directory with command `touch Dockerfile` and fill in the portal configuration

Step 2: Built a jar package of the project using the Maven package build in IntelliJ IDEA

Step 3: Containerize the project by building an image and tagging it as springio/rest-service using the command `docker build -t springio/rest-service .`
You can use the command `docker images` to check the images and use the command `java -jar target/rest-service-0.0.1-SNAPSHOT.jar` to run the RESTful web service.

Step 4: Finally, run the command `docker run -p 8080:8080 springio/rest-service` to actually run the image you just built and check the status using `docker ps`. Visit `http://localhost:8080/greeting` to view the actual web service.

Reference: 

[Official Document](https://spring.io/guides/gs/spring-boot-docker/)

[Tutorial](https://www.cnblogs.com/cloudfloating/p/10851315.html)

[Video](https://www.youtube.com/watch?v=FlSup_eelYE)

[Build jar package](https://blog.csdn.net/yuanting_/article/details/90207328)

## Task 4: Set up Swagger2 for the service
Reference: https://www.baeldung.com/swagger-2-documentation-for-spring-rest-api

Setup and be able to query your service API from the Swagger UI

## Task 5: Set up DB
- Setup local MySQL
- List the difference between DB persistent frameworks. Eg: Mybatis, JDBC, Hibernate
- Connect your service to be able query DB using Mybatis.

