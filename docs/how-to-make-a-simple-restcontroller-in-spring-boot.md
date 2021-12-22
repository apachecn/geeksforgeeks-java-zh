# 如何在 Spring Boot 做一个简单的 RestController？

> 原文:[https://www . geesforgeks . org/如何制作简单的春季开机 rest controller/](https://www.geeksforgeeks.org/how-to-make-a-simple-restcontroller-in-spring-boot/)

Spring Boot 建在春天的顶端，包含了春天的所有特征。由于其快速的生产就绪环境，开发人员能够直接专注于逻辑，而不是纠结于配置和设置，因此正成为开发人员的最爱。Spring Boot 是一个基于微服务的框架，在其中制作一个生产就绪的应用程序只需要很少的时间。在本文中，我们将讨论如何在 Spring Boot 制作一个简单的 restcontroller。

> **rest controller**:rest controller 用于借助@restcontroller 注释制作 restful web 服务。此注释在类级别使用，允许类处理客户端发出的请求。让我们用一个例子来理解@restcontroller 注释。

[Spring Initializr](https://start.spring.io/) 是一个基于 web 的工具，使用它我们可以很容易地生成 Spring Boot 项目的结构。它还为元数据模型中表达的项目提供了各种不同的特性。这个模型允许我们配置 JVM 支持的依赖列表。在这里，我们将使用 spring 初始化器创建应用程序的结构，然后使用 IDE 创建一个示例 GET 路由。因此，要做到这一点，依次遵循以下步骤:

**步骤 1:** 转到春季初始化

按照要求填写细节。对于此应用:

```java
Project: Maven
Language: Java
Spring Boot: 2.2.8
Packaging: JAR
Java: 8
Dependencies: Spring Web 
```

**第 2 步:**点击生成，将下载启动项目

**第三步:**提取 zip 文件。现在打开一个合适的 IDE，然后转到**文件>从现有来源新建>项目> Spring-boot-app** 并选择 pom.xml。在提示符下单击导入更改并等待项目同步，如下图所示:

![](img/938bf65050c80f1ce86dbf17ba3d2b23.png)

> **注意**:在 Maven 的导入项目窗口中，确保选择了创建项目时选择的相同版本的 JDK。

**第四步:**转到 src >主界面>java>com . gfg . spring . boot . app，创建一个名为 Controller 的 Java 类，并添加注释 **@RestController** 。

**Controller.java 文件:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
@RestController

// Class
public class Controller {

   @GetMapping("/hello/{name}/{age}")
   public void insert(@PathVariable("name") String name, @PathVariable("age") int age) {

       // Print and display name and age
       System.out.println(name);
       System.out.println(age);
   }
```

这个应用程序现在可以运行了。

**第五步:**运行 SpringBootAppApplication 类，等待 Tomcat 服务器启动。

![](img/093e5180d109d63d4fd76cdf5ca54c15.png)

> **注意**:Tomcat 服务器的默认端口是 8080，可以在 application.properties 文件中更改。

这个 controller.java 文件用于处理来自客户端的所有传入请求。