# Java 中 JDBC 和 Hibernate 的区别

> 原文:[https://www . geesforgeks . org/Java 中 jdbc 和 hibernate 的区别/](https://www.geeksforgeeks.org/difference-between-jdbc-and-hibernate-in-java/)

Java 是当前场景中最强大和最流行的服务器端语言之一。服务器端语言的主要特征之一是与数据库通信的能力。在本文中，让我们了解 JDBC 和 Hibernate 这两种连接数据库的方式之间的区别。

在讨论这些差异之前，让我们先了解它们各自的真正含义。

**[JDBC](https://www.geeksforgeeks.org/establishing-jdbc-connection-in-java/) :** JDBC 代表 **Java 数据库连接**。它是一个 java 应用程序编程接口，提供了 Java 编程语言和各种数据库之间的连接(即，它在两者之间建立了一个链接，以便程序员可以从 Java 代码发送数据并将其存储在数据库中以备将来使用)。

**Hibernate:**Hibernate 是一个开源、无入侵、轻量级的 java ORM( **对象-关系映射**)框架，用于开发独立于数据库软件的对象，并在 JEE 的所有 java 中进行独立的持久化逻辑。它简化了 java 应用程序与数据库的交互。Hibernate 是 JPA(Java 持久性 API)的一个实现。

下表描述了差异:

| s。不 | JDBC | Hibernation |
| --- | --- | --- |
| 1\. | In JDBC, you need to write code to map the data representation of object model to the schema of relational model. | Hibernate maps the data of the object model to the schema of the database itself with the help of annotations. |
| 2。 | JDBC enables developers to create queries using Structured Query Language (SQL) and update data to relational databases. | Hibernate uses HQL (Hibernate Query Language), which is similar to SQL, but understands the object-oriented concepts such as inheritance and association. | 3。 | JDBC code needs to be written in a try catch block because it throws a checked exception (SQLexception). | Hibernate manages the exception itself by marking the exception as unchecked. |
| 4。 | JDBC depends on databases, that is, different codes need to be written for different databases. | Hibernate is independent of databases, and the same code can be applied to many databases with only a little change. |
| 5。 | In JDBC, it is quite difficult to establish relationships. | One-to-one, one-to-many, many-to-one and many-to-many associations can be easily obtained with the help of labeling. |