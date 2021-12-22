# Java–JPA vs Hibernate

> 原文:[https://www.geeksforgeeks.org/java-jpa-vs-hibernate/](https://www.geeksforgeeks.org/java-jpa-vs-hibernate/)

**JPA** 代表 Java 持久性 API(应用编程接口)。最初于 2006 年 5 月 11 日发行。这是一个 Java 规范，为 ORM 工具提供了一些功能和标准。它用于检查、控制和保存 Java 对象和关系数据库之间的数据。它被视为对象关系映射的标准技术。

它被认为是面向对象模型和关系数据库系统之间的纽带。由于它是 Java 的一个规范，JPA 本身不执行任何功能。因此，需要实施。因此，对于数据持久性，像 Hibernate 这样的 ORM 工具实现了 JPA 规范。对于数据持久性， **javax.persistence** 包包含 JPA 类和接口。

让我们讨论一下联合行动计划的一些主要特点，如下所示:

*   JPA 只是一个规范，它不是一个实现。
*   它是一组规则和指南，用于设置实现对象关系映射的接口。
*   它需要一些类和接口。
*   它支持简单、清晰和同化的对象关系映射。
*   它支持多态性和继承。
*   动态和命名查询可以包含在 JPA 中。

现在我们需要加入一个框架来讨论。是的，你猜对了，冬眠。这是一个 java 框架、开源、轻量级和面向 java 语言的 ORM(对象关系映射)工具，它简化了 Java 应用程序的构建以与数据库交互。它用于保存关系数据库系统中的 Java 对象。

> **注:** Hibernate ORM 框架由红帽设计。最初于 2007 年 5 月 23 日发行。它支持跨平台 JVM，并且是用 Java 编写的。

**Hibernate** 的主要功能是将 Java 类映射到数据库表。以下是 Hibernate 的一些关键特性:

*   Hibernate 是 JPA 准则的一个实现。
*   它有助于将 Java 数据类型映射到 SQL 数据类型。
*   它是 JPA 的贡献者。

现在你一定想知道为什么需要 JPA，对吧。因此，让我们先讨论联合行动计划的必要性，然后再讨论它们之间的差异，从而找出它们之间的巨大差异。所以如图所示，JPA 是一个规范。它为 ORM 工具提供了通用的功能和原型。所有 ORM 工具(如 Hibernate)都遵循公共标准，执行相同的规范。随后，如果我们需要将我们的应用程序从一个 ORM 工具切换到另一个，那么我们可以很容易地做到这一点。

到目前为止，我们已经讨论了这两个概念及其合适的需求。现在让我们跳到 JPA 和 hibernate 之间的区别，并总结一下这篇文章。正如我们所知，JPA 只是一个规范，这意味着没有实现。我们可以用 JPA 注释将类注释到我们想要的程度，尽管没有实现什么都不会发生。假设 JPA 是应该遵循的准则，但是，Hibernate 是一个 JPA 实现代码，它按照 JPA 规范的描述统一了 API，并提供了匿名功能。

以下是 JPA 和 Hibernate 的区别:

<figure class="table">

| 

**JPA**

 | 

**Hibernate**

 |
| --- | --- |
| 作业的装配区（JobPackArea）是在 **javax.persistence** 包中描述的。 | 冬眠在**组织休眠**包中描述。 |
| It describes the processing of relational data in Java applications. | Hibernate 是一个对象-关系映射(ORM)工具，用于保存关系数据库系统中的 Java 对象。

 |
| It is not an implementation. It is just a Java specification. | Hibernate is an implementation of JPA. Therefore, the general standard **given by JPA is** followed by Hibernate. |
| 它是一个允许执行数据库操作的标准 API。 | 用于 Java 数据类型与 SQL 数据类型、数据库表的映射。 |
| 作为一种面向对象的查询语言，它使用 **Java 持久性查询语言(JPQL)** 来执行数据库操作。 | 作为一种面向对象的查询语言，它使用 **Hibernate 查询语言(HQL)** 来执行数据库操作。 |
| 为持久化单元与实体管理器工厂互联，它使用 **EntityManagerFactory** 接口。因此，它给出了一个实体管理器。 | Create a session instance and use the **session factory** interface. |
| 要对映射的实体类的实例进行操作、读取操作和移除操作，它使用 **EntityManager** 界面。该接口将 **s** 与持续条件互连。 | 使用**会话**界面对映射的实体类实例进行动作、读取动作和移除动作。它充当 Java 应用程序和 Hibernate 之间的运行时接口。 |

</figure>

> **结论:**Hibernate 和 JPA 的主要区别在于 Hibernate 是框架，而 JPA 是 API 规范。Hibernate 是所有 JPA 准则的实现。