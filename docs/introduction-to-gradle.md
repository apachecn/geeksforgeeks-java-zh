# Gradle 简介

> 原文:[https://www.geeksforgeeks.org/introduction-to-gradle/](https://www.geeksforgeeks.org/introduction-to-gradle/)

[**Gradle**](https://en.wikipedia.org/wiki/Gradle) 是一个优秀的开源构建工具，能够开发任何一种软件。13 年前，这个工具是由一群名叫汉斯·多克特、斯泽潘·费伯·亚当·默多克、卢克·达雷、彼得·尼德维瑟、达斯·德博和雷内·格罗什克贝福的开发人员开发的。这是一个基于 Apache Ant 和 [Apache Maven](https://www.geeksforgeeks.org/introduction-apache-maven-build-automation-tool-java-projects/) 的自动化工具。该工具能够开发符合行业标准的应用，支持多种语言，包括 [Groovy](https://www.geeksforgeeks.org/difference-between-groovy-and-java/) 、 [C++](https://www.geeksforgeeks.org/c-plus-plus/) 、 [Java](https://www.geeksforgeeks.org/java/) 、 [Scala](https://www.geeksforgeeks.org/scala-programming-language/) 、 [C](https://www.geeksforgeeks.org/c/) 。Gradle 还能够控制从编译和打包到测试、部署和发布的开发任务。

#### 格拉德勒历史

与蚂蚁和马文相比，Gradle 是最稳定的工具。该工具于 2007 年末发布，最初是作为前辈的替代品，不仅取代了他们，还弥补了他们的缺点。它的稳定版本于 2019 年发布，目前是最新的 6.6 版本。

### 格拉德勒的工作

Gradle 项目在建造时由一个或多个**项目**组成。这些项目包括**任务**。让我们了解这两个术语的基础。

**1。gradlee 项目:**gradlee 创建的项目是一个 web 应用程序或一个 [JAR 文件](https://www.geeksforgeeks.org/jar-files-java/)。这些项目是一个或多个任务的组合。这些项目能够部署在不同的开发生命周期中。一个梯度项目可以描述为用 N 块砖砌墙，这可以称为任务。
**2。分级任务:**任务是负责特定角色的功能。这些任务负责创建类、Javadoc 或将档案发布到存储库中，这使得 Gradle 项目的整个开发成为可能。这些任务帮助 Gradle 决定要为特定输出处理什么输入。同样，任务可以分为两种不同的方式:

*   **默认任务:**这些是由 Gradle 提供给用户的预定义任务。这些任务在用户自己不声明任何任务时执行之前提供给用户。例如，将提供给用户的默认任务初始化并包装到一个 Gradle 项目中
*   **自定义任务:**自定义任务是开发人员为执行用户定义的任务而开发的任务。这些是为在项目中运行特定角色而开发的。下面让我们看看如何开发一个自定义任务。

**示例:**打印欢迎来到极客 forGeeks！在格雷尔有一项任务。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
build.gradle : task hello
{
    doLast
    {
        println 'Welcome to GeeksforGeeks!'
    }
}
```

**输出:**

```java
> gradle -q hello
Welcome to GeeksforGeeks!
```

### 渐变的特点:

*   **IDE 支持:** Gradle 支持多种 IDE(集成开发环境)。这是一个支持多种开发环境的构建工具。
*   **熟悉 Java:** Gradle 项目需要 Java 环境 [JVM](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/) 才能运行。Gradle 的特性也类似于 Java。它还支持由 Java 支持的[应用编程接口](https://www.geeksforgeeks.org/introduction-to-apis/)，这对开发人员来说是最大的优势，它使它变得通用。
*   **任务&存储库支持:** Gradle 工具支持 Ant 和 Maven 构建工具的特性。它允许将 Ant 项目导入到 Gradle 环境中。它还支持导入 [Maven 存储库](https://www.geeksforgeeks.org/introduction-apache-maven-build-automation-tool-java-projects/)，并允许在现有项目中使用基础设施。
*   **构建:** Gradle 只为必要的任务提供构建，就好像它只编译上次构建之前所做的更改一样。它减少了装载时间。
*   **免费开源:**gradlee 是一个开源构建的工具，使其对用户友好，并根据 ASL (Apache License)获得许可。
*   **多设计构建支持:** Gradle 构建工具实现了多构建支持，因为在设计根项目时，它可能包含几个子项目，并且这些项目可以有多个更多的项目。在 Gradle 的帮助下，可以轻松构建布局。

### 使用 Gradle 的优点

*   **声明性构建:**Gradle 的 Groovy 语言提供了声明性语言元素。它检查以前的源代码是否有变化，然后编译。
*   **可扩展性:**使用 Gradle 创建的应用程序具有很高的可扩展性，因为它提高了生产效率。它允许我们在模型基础设施中工作，这有助于工作变得有条理。
*   **深度 API:** 有了这个 API 的支持，开发者可以轻松定制配置，监控执行行为。
*   **免费开源:** Gradle 是一个开源项目，有很好的社区支持。
*   **移动方便:** Gradle 具有适应任何项目结构的特点。它还支持插件的创建，这有助于项目开发。

### 使用 Gradle 的缺点

*   **技术专长:**要构建具有梯度优先技术技能的任务，需要。
*   **语言依赖:**要使用 Gradle，需要具备 Groovy 或 Java 语言的基础知识。
*   **集成:**添加功能相当复杂，因为它需要在投入使用之前进行正确配置。
*   **可理解性:** Gradle 文档相当全面。它需要事先了解术语。