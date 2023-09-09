---
layout: post 
title: Java SE, Java EE, and Spring Framework
category: 随想
---

I didn't know what exactly Java EE is for a long time. After reading a whole bunch of documents from Spring/Eclipse/Wikipedia, finally I understand the relationship between those technologies.

### Java SE

Java Standard Edition is what usually we call 'Java'. OpenJDK is the official reference implementation. It consists of both Java Language Specification, Java Library, and Java Virtual Machine Specification. So Java SE and JDK can be used interchangeably.

### Java EE

Java Enterprise Edition is a collection of specifications. It consists of APIs like web service(Servlet), persistence(JPA), Bean validation, Json data-bind, annotation, mail, and transaction management. To use these specifications, you will have to import both the specification itself and its implementation. For example, if you want to write a web server, you will have to write it with Servlet and let your program run in a Servlet container like Apache Tomcat or Jetty. If you want operation with a database, you will probably use JPA and one of its implementation Hibernate ORM.
In a nutshell, Java EE is a series of specifications that can boost the development of enterprise Java programs. There may be multiple implementations for every specification, such as Jetty, Glassfish, and Apache Tomcat for Servlet.

### Spring Framework

You may consider it strange to place Spring here because it does different things with Java SE and Java EE. However, according to Spring's documentation, it does have some relationship with them. Spring was started as a response to the complexity of J2EE, it selects some specific Java EE specifications like Servlet instead of embracing the whole of it, which makes Spring more light-weighted and easier to use.