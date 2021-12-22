# 在 Java 中，CompileTime 类路径与 RunTime 类路径有何不同？

> 原文:[https://www . geesforgeks . org/how-is-compiletime-class path-异于-runtime-classpath-in-java/](https://www.geeksforgeeks.org/how-is-compiletime-classpath-different-from-runtime-classpath-in-java/)

<u>**什么是[类路径](https://www.geeksforgeeks.org/classpath-in-java/)？**</u>
[类路径](https://www.geeksforgeeks.org/classpath-in-java/)是指所有类/罐子都可用的路径。

<u>**什么是编译时类路径？**</u>
这个类路径拥有编译应用程序所需的所有类/jar，没有任何语法错误。

现在我们可能认为我们的项目编译成功了，所以它会很好地执行。但这并不总是正确的，因为在某些情况下(如下所述)，要成功执行项目，您可能需要在运行时使用一些其他类/jar。这就是为什么运行时类路径会出现在图片中。

<u>**什么是运行时类路径？**</u>
类路径包含成功执行应用程序所需的所有类/jar。

<u>**设置类路径**</u> :只需在 pom.xml 文件中添加依赖项，就会自动在类路径中添加 jars。

## 示例 pom.xml

```
<project 
         xmlns="http://maven.apache.org/POM/4.0.0" 
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0   
                 http://maven.apache.org/xsd/maven-4.0.0.xsd">

    <modelVersion>4.0.0</modelVersion>

    <groupId>com.softvision</groupId>
    <artifactId>SpringMVC</artifactId>
    <packaging>war</packaging>
    <version>1.0-SNAPSHOT</version>
    <name>SpringMVC Json Webapp</name>
    <url>http://maven.apache.org</url>

    <properties>
        <spring.version>3.2.2.RELEASE</spring.version>
        <jackson.version>1.9.10</jackson.version>
        <jdk.version>1.6</jdk.version>
    </properties>

    <dependencies>

        <!-- Spring 3 dependencies -->
        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-core</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-web</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <dependency>
            <groupId>org.springframework</groupId>
            <artifactId>spring-webmvc</artifactId>
            <version>${spring.version}</version>
        </dependency>

        <!-- Jackson JSON Mapper -->
        <dependency>
            <groupId>org.codehaus.jackson</groupId>
            <artifactId>jackson-mapper-asl</artifactId>
            <version>${jackson.version}</version>
        </dependency>

    </dependencies>

</project>
```

**Note**: Classpath setting will be done by eclipse or any other IDE automatically. This can’t be shown here.

<u>**CompileTime 类路径与 RunTime 类路径有何不同？**T3】</u>

*   **Case-1**: Let’s say we are developing a [Spring-MVC](https://www.geeksforgeeks.org/spring-mvc-with-jsp-view/) web application to post the [JSON data](https://www.geeksforgeeks.org/json-data-types/). So in order to achieve it, we need [Jackson jar](https://www.geeksforgeeks.org/convert-java-object-to-json-string-using-jackson-api/) to map the [JSON data](https://www.geeksforgeeks.org/json-data-types/) to the DTO class. If we don’t have this jar in the classpath then at the compile time we won’t get any error but our application will not execute properly because it needs Jackson for data binding at the runtime that is not available.

    这就是为什么我们说编译时和运行时类路径是不同的。

*   **Case-2**: While developing [servlet based application](https://www.geeksforgeeks.org/introduction-java-servlets/) we need **servlet-api.jar** so we can use **HttpServlet**, **HttpServletRequest**, **HttpServletResponse**, etc while writing code and end up in no compilation error. At this point, we are using **servlet-API** that is just specification not the actual implementation of the servlet-API.

    实际上，实现是运行基于 servlet 的应用程序所需的 JEE 容器。因此，我想说的是，当运行这样一个应用程序时，JEE 容器将在运行时提供实现类来成功运行它，而没有 JEE 容器，应用程序将无法运行。