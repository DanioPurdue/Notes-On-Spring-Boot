POJO: 

Springs uses aspecting for almost all of its actions. 

ApplicationContext: factory method, every contexts

SpringBoot: cloud native ready but runs in traditional environment

SpringBoot: Embedded Tomcat application server

automatic servlet mappings

Package name equal to group name

## Spring Framework

IOC container

## Spring Boot

Setup & Configuration is hard

xml

microservices

Pros:

Convention over Configuration:

Spring CLI, entry Point, starter POMs, give us production ready feature.

## Dependency management

All the dependencies that are downloaded from the website are starter projects in maven dependency.



**Why is the Package Name option so critical for a Spring Boot project?**

It is where the Application Class will be created and provides the base for component scanning.



![image-20190706233916429](/Users/daniowang/OneDrive/GitHub/Notes-On-Spring-Boot/annotation.png)

## Embedded Database and Configuration

If you have your own schema and data, make sure you have the following thing in your property sheet, otherwise hibernate would wipe out everything you have set up before.

```java
spring.jpa.hibernate.ddl-auto=none
```

## Spring Data

Reduction of the boilerplate code. Provides ability to swap out datasources much easier. 

Key Components:

1. repository: interface that goes back the traditional repository
2. entity: 

Spring data allows you to have dynamic query generation

Setup of 

