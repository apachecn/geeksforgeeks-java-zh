# EJB 和春天的区别

> 原文:[https://www . geesforgeks . org/EJB 和 spring 之间的区别/](https://www.geeksforgeeks.org/difference-between-ejb-and-spring/)

EJB 和 Spring 都用于开发企业应用程序。但是他们之间几乎没有什么区别。因此，在本文中，我们试图涵盖所有这些差异。

**1。[企业爪哇豆(EJB)](https://www.geeksforgeeks.org/enterprise-java-beans-ejb/) :**
EJB 代表企业爪哇豆。它是一个服务器端软件组件，用于总结应用程序的业务逻辑。EJB 容器为网络相关软件元素提供了运行时环境，包括计算机可靠性、Java Servlet 生命周期(JSL)管理、事务过程和其他网络服务。要运行一个 EJB 应用程序，我们需要一个应用服务器，如 Jboss、Glassfish、Weblogic、Websphere 等。它执行生命周期管理、对象池、事务处理、安全性等。EJB 有三种类型。

*   **会话 Bean–**
    会话 Bean 包含可由本地、远程或 webservice 客户端调用的业务逻辑。会话豆有两种类型:
    **(i)。**有状态会话 bean 和**(二)。**无状态会话 bean。
*   **消息驱动 Bean–**
    像会话 Bean 一样，它包含业务逻辑，但通过传递消息来调用。

*   **Entity Bean –**
    It summarizes the state that can be persisted in the database. It is deprecated. Now, it is replaced with JPA (Java Persistent API). There are two types of entity bean :
    **(i).** Bean Managed Persistence and **(ii).** Container Managed Persistence.

    **2。 [Spring](https://www.geeksforgeeks.org/introduction-to-spring-framework/) :**
    Spring 是一个开源的轻量级框架，允许 Java EE 7 开发人员构建简单、可靠、可扩展的企业应用。该框架使用各种技术来开发企业应用程序，例如面向方面编程(AOP)、普通旧 Java 对象(POJO)和依赖注入(DI)。这个框架帮助您管理业务对象。与传统的 Java 框架和应用程序编程接口相比，它使网络应用程序的开发变得更加容易，例如 Java 数据库连接(JDBC)、Java 服务器页面(JSP)和 Java Servlet。Spring 框架的特性，如控制反转(IoC)、面向方面编程(AOP)和事务管理，使其在框架列表中独一无二。

    **EJB 和春天的区别:**

    <center>

    | 性能 | EJB | 春天 |
    | 规格 | EJB 是 Java EE 的一个规范。 | 春天是一个框架。 |
    | 依赖注入 | 它可以在容器中注入任何东西，包括 EJB 数据源、JMS 资源和 JPA 资源。 | 它可以注入任何东西，包括列表、属性、地图和 JNDI 资源。 |
    | 事务管理 | 它只支持 JTA 事务管理器。 | 它支持多个事务管理器，如 JTA、JDBC 和 Hibernate。 |
    | 坚持 | 它与 JPA 紧密集成。 | 它支持各种持久性技术，如 JDBC、Hibernate、JPA 和 iBatis。 |
    | 信息发送 | 它通过消息驱动 Beans 提供现成的消息传递功能。 | 我们需要为每条消息添加监听器配置。 |
    | 行程安排 | 它通过 EJB 时间服务提供简单的时间安排。 | 我们需要添加和配置石英进行调度。 |
    | 安全 | 它通过 JAAS 支持声明性和编程性安全。 | 它通过 Spring 配置文件提供声明性安全性。 |
    | 面向切面编程 | 它通过拦截器提供有限的支持。 | 它通过 AspectJ 提供了强大的支持。 |

    </center>