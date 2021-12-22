# 企业爪哇豆(EJB)

> 原文:[https://www.geeksforgeeks.org/enterprise-java-beans-ejb/](https://www.geeksforgeeks.org/enterprise-java-beans-ejb/)

企业 Java bean(EJB)是企业软件标准制造的几个 Java APIs 之一。EJB 是一个服务器端软件元素，它总结了应用程序的业务逻辑。企业级 Java Beans web 存储库为 web 相关软件元素提供了一个运行时域，包括计算机可靠性、Java Servlet 生命周期(JSL)管理、事务过程和其他 web 服务。EJB 枚举是 Java EE 枚举的一个子集。

EJB 枚举最初是由 IBM 在 1997 年开发的，后来被太阳微系统公司在 1999 年采用，并在 Java 社区过程中得到增强。

EJB 枚举旨在提供一种标准方式来实现企业应用程序中常见的服务器端业务软件。这样的机器代码解决了相同类型的问题，并且这些问题的解决方案经常被程序员重复地重新实现。企业 Java Beans 被假定以一种标准的方式管理诸如持久性、事务诚实性和安全性等常见问题，这使得程序员可以自由地专注于手头企业软件的特定部分。

要运行 EJB 应用程序，我们需要一个应用服务器(EJB 容器)，如 Jboss、Glassfish、Weblogic、Websphere 等。它执行:

**1。**生命周期管理
T3】2。安防
T6】3。交易管理
**4。**对象池

**企业 Java 豆的类型**

EJB 有**三种**类型:
T3】1。*会话 Bean:* 会话 Bean 包含可由本地、远程或 webservice 客户端调用的业务逻辑。有两种类型的会话 bean:(一)有状态会话 bean 和(二)无状态会话 bean。

*   **(i)有状态会话 bean :**
    有状态会话 bean 在状态的帮助下执行业务任务。通过将信息存储在实例变量中，有状态会话 bean 可用于访问各种方法调用。有些应用程序需要在不同的方法调用中存储信息。在购物网站中，客户选择的商品必须存储为数据，这是有状态会话 bean 的一个例子。
*   **(ii)无状态会话 bean :**
    无状态会话 bean 实现了业务逻辑，而没有持久的存储机制，比如状态或数据库，可以使用共享数据。无状态会话 bean 可用于不需要跨调用方法使用信息的情况。

**2。*消息驱动 Bean:*** 像会话 Bean 一样，它包含业务逻辑，但通过传递消息来调用。
**3。*实体 Bean:*** 它总结了数据库中可以保留的状态。不推荐使用。现在，它被 JPA (Java 持久性 API)所取代。实体 bean 有两种类型:

*   **(i) bean 托管持久性:**
    在 Bean 托管持久性类型的实体 Bean 中，程序员必须为数据库调用编写代码。它跨多个会话和多个客户端持续存在。

*   **(ii) Container Managed Persistence :**
    Container managed persistence are enterprise bean that persists across database. In container managed persistence the container take care of database calls.

    **何时使用企业 Java bean**

    **1。应用程序需要远程访问。**换句话说就是分布式的。
    T3】2。应用程序需要可扩展。 EJB 应用支持负载平衡、集群和故障转移。
    **3。应用程序需要封装的业务逻辑。** EJB 应用区分于示范层和持续层。

    **企业级 Java 豆的优势**

    **1。** EJB 存储库为企业 bean 提供系统级服务，bean 开发人员可以专注于解决业务问题。不是 bean 开发人员，而是 EJB 存储库负责系统级服务，如事务管理和安全授权。
    T3】2。bean 而不是客户端包含应用程序的业务逻辑，客户端开发人员可以专注于客户端的呈现。客户端开发人员不必为执行业务规则或访问数据库的模式编写代码。因此，客户端更薄，这对运行在小型设备上的客户端尤为重要。
    **3。**企业 Java Beans 是可移植的元素，应用程序组装者可以从已经存在的 bean 中构建新的应用程序。

    **企业 Java 豆的劣势**

    **1。**需要应用服务器
    **2。**只需要 java 客户端。对于其他语言客户端，您需要使用 webservice。
    **3。**理解和开发 EJB 应用程序的复杂性。