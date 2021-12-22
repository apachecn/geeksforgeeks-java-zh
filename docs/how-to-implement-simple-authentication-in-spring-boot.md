# 如何在 Spring Boot 实现简单认证？

> 原文:[https://www . geesforgeks . org/如何实现简单的春季启动身份验证/](https://www.geeksforgeeks.org/how-to-implement-simple-authentication-in-spring-boot/)

**Java 语言**是所有编程语言中最流行的语言之一。使用 java 编程语言有几个优点，无论是出于安全目的还是构建大型分发项目。使用 Java 的优势之一是，它试图借助类、继承、多态等概念将语言中的每个概念与现实世界联系起来。java 中还有其他几个概念，增加了 java 代码和程序员之间的用户友好交互，例如泛型、访问说明符、注释等。这些特性为类以及 java 程序的方法增加了一个额外的属性。在本文中，我们将讨论如何在 spring boot 中实现简单身份验证。**认证**是任何一种安全的主要步骤之一。Spring 提供了依赖项，即 Spring 安全性，它有助于在应用编程接口上建立身份验证。

> **注**:首先我们需要在我们的项目中建立 spring 应用。

Spring Initializr 是一个基于网络的工具，使用它我们可以很容易地生成 Spring Boot 项目的结构。它还为元数据模型中表达的项目提供了各种不同的特性。这个模型允许我们配置 JVM 支持的依赖列表。在这里，我们将使用 spring 初始化器创建应用程序的结构，然后使用 IDE 创建一个示例 GET 路由。因此，要做到这一点，依次遵循以下步骤:

**第一步:**转到[春天初始化](https://start.spring.io/)

按照要求填写细节。对于此应用:

```java
Project: Maven
Language: Java
Spring Boot: 2.4.12
Packaging: JAR
Java: 8
Dependencies: Spring Web, Spring Security
```

![](img/56491d5b07a7b31cc96ea9c9aeadbeef.png)

**第二步:**提取 zip 文件。现在打开一个合适的 IDE，然后转到**文件>从现有来源新建>项目> Spring-boot-app** 并选择 pom.xml。在提示中点击导入更改并等待项目同步。

![](img/938bf65050c80f1ce86dbf17ba3d2b23.png)

> **注意**:在 Maven 的导入项目窗口中，确保选择了创建项目时选择的相同版本的 JDK。

**第三步:**前往 src >主>Java>com . gfg . spring . boot . app>SpringBootAppApplication.java

**SpringBootAppApplication.java**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
@SpringBootApplication
public class SpringSecurityApplication {

    public static void main(String[] args) {
        SpringApplication.run(SpringSecurityApplication.class, args);
    }
}
```