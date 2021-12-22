# JDBC–4 型驾驶员

> 原文:[https://www.geeksforgeeks.org/jdbc-type-4-driver/](https://www.geeksforgeeks.org/jdbc-type-4-driver/)

为了更好地理解什么是类型 4 驱动程序，让我们对 JDBC 和以前的 ODBC 做一个概述。一个 [**JDBC 驱动程序**](https://www.geeksforgeeks.org/jdbc-drivers/) 使 Java 应用程序能够与数据库交互，我们可以从中获取或存储数据。JDBC 驱动程序类似于 ODBC 驱动程序。JDBC 类包含在 Java 包中

*   连接到数据源，如数据库。
*   向数据库发送查询和更新语句
*   检索并处理从数据库接收的结果，以响应您的查询

JDK 附带的 Java.sql 包包含各种定义了行为的类，它们的实际实现是在第三方驱动程序中完成的。第三方供应商在其数据库驱动程序中实现 [java.sql.Driver](https://www.geeksforgeeks.org/jdbc-drivers/) 接口。

![](img/18c429c18efdacf6b79e3adff68c1b0e.png)

[**【ODBC】**](https://www.geeksforgeeks.org/odbc-full-form/)**基于设备驱动模型，驱动封装了将一组标准命令和函数转换为底层系统所需的特定调用所需的逻辑。**

**JDBC 驱动程序类型用于对用于连接数据库的技术进行分类。**

1.  **1 型桥驱动器**
2.  **类型 2 本地应用编程接口**
3.  **类型 3 网络协议**
4.  **第 4 类本地协议**

**Type-4 驱动程序也称为本机协议驱动程序。这个驱动程序直接与数据库交互。它不需要任何本机数据库库，这就是它也被称为精简驱动程序的原因。**

*   **不需要任何本机库和中间件服务器，因此无需客户端或服务器端安装。**
*   **它完全是用 Java 语言编写的，因此它们是可移植的驱动程序。**

> **[Type-4 JDBC 驱动程序](https://www.geeksforgeeks.org/jdbc-drivers/)也称为“瘦驱动程序”或[直接到数据库纯 Java 驱动程序](https://www.geeksforgeeks.org/jdbc-drivers/)。它是便携式的，是所有 JDBC 驱动程序中最快的，并且依赖于数据库。**

**瘦驱动程序将 JDBC 调用直接转换为供应商特定的数据库协议。它完全用 Java 语言编写。此外，它是独立于平台的驱动程序，但它依赖于数据库，因为它使用本机协议(协议只能在特定服务器之间建立连接)。**

**[**【瘦驱动】**](https://www.geeksforgeeks.org/jdbc-drivers/) 安装在客户端的 Java 虚拟机内部。**

*   **不需要客户端或服务器上的特殊软件。不使用翻译或中间件层，提高了性能。**
*   **独立于平台(完全用 Java 编码)**
*   **不需要安装本机库。**
*   **它使用特定于数据库服务器的协议，使其安全。**
*   **有助于调试，因为 JVM 可以管理应用程序到数据库连接的所有方面。**
*   **它使用特定于数据库的协议，并且依赖于数据库管理系统供应商**
*   **可攀登的**
*   **高级系统管理**
*   **性能优越**
*   **高级 Java 功能集**
*   **提供比 JDBC/ODBC 桥和类型 2 驱动程序明显更好的性能**

**如果您正在访问一种类型的数据库，如 Oracle、Sybase 或 IBM，首选的驱动程序类型是 type-4。**

****支持 Unicode】****

**使用 Type 4 JDBC 驱动程序访问 Unicode 和非 Unicode 支持的数据库，可以在 JDBC 的任何操作系统平台上开发多语言应用程序。在内部，Java 应用程序对字符串数据使用 UTF-16 Unicode 编码。获取数据时，类型 4 JDBC 驱动程序会自动执行从数据库使用的字符编码到 UTF-16 的转换。同样，在数据库中插入或更新数据时，驱动程序会自动将 UTF-16 编码转换为数据库使用的字符编码。**

**让我们讨论一下类型 4 JDBC 驱动程序中的错误处理，因为类型 4 JDBC 驱动程序被报告通过抛出 SQLExceptions 向调用应用程序抛出错误。这是因为每个 SQLException 都包含:**

1.  **本机错误代码**
2.  **错误原因的描述**
3.  **包含 XOPEN [SQLstate](https://www.geeksforgeeks.org/postgresql-errors-and-messages/) 的字符串**