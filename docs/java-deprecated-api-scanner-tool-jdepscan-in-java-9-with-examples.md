# Java 9 中的 Java 弃用 API 扫描器工具(jdepscan)示例

> 原文:[https://www . geesforgeks . org/Java-弃用-API-scanner-tool-jdepscan-in-Java-9-with-examples/](https://www.geeksforgeeks.org/java-deprecated-api-scanner-tool-jdepscan-in-java-9-with-examples/)

**Java 弃用 API Scanner 工具** : Java 弃用 API Scanner 工具即 **jdeprscan** 是一款静态分析命令行工具，在 JDK 9 中推出，用于找出弃用 API 在给定输入中的用途。这里的输入可以是。类文件名、目录或 JAR 文件。每当我们向 jdeprscan 命令行工具提供任何输入时，它都会生成系统控制台的依赖项。jdeprscan 引入了影响输出的各种选项。根据选项，jdeprscan 命令行工具生成输出。jdeprscan 工具识别由 Java SE 不推荐使用的 API 定义的不推荐使用的 API，但它不会列出第三方库使用的不推荐使用的 API。

**使用 jdeprscan 工具的语法:**

```java
jdeprscan [options] {class|dir|jar}

```

**示例:**

```java
// Program to illustrate the output of jdeprscan tool

import java.awt.*;
class Geeks extends Thread {
    public void run()
    {
        System.out.println("Child Thread");
    }

    public static void main(String args[])
    {
        Thread thread = new Thread();
        thread.start();
        thread.stop();

        List list = new List();
        list.addItem("Geeksforgeeks");

        Integer i = new Integer(100);
        System.out.println(i);
    }
}
```

**编译时控制台:**

```java
Note: Geeks.java uses or overrides a deprecated API.
Note: Recompile with -Xlint:deprecation for details.

```

[![](img/2bfca06bcaa4f76b342b6b4d03d1f991.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200128155937/Capture342.png)

**输出:**

```java
jdeprscan Geeks.class
```

[![](img/501071457291d521d09e3b4083b55dfa.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200128160859/Capture346.png)

【jdeprscan 可用的各种选项:

1.  **–release 6|7|8|9**: It will list out the uses of deprecated APIs in the given argument as per given release. Suppose we are using JDK 9 and we want to list out the deprecated APIs as per Java release 7, then we can use this option.

    **输出:**

    ```java
    jdeprscan --release 6  Geeks.class
    ```

    [![](img/46723bf7ad69f45bb3557e3e4f7613d5.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200128161022/Capture347.png)

    ```java
    jdeprscan --release 7  Geeks.class
    ```

    [![](img/a2f5083c97a125a754a6c9d93a5a3847.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200128161144/Capture348.png)

2.  **–verbose**: It will enable printing of additional message during listing out deprecated APIs.

    **输出:**

    ```java
    jdeprscan --verbose Geeks.class
    ```

    [![](img/12a056f27edd42d1ac2af73ca2ae9569.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200128161428/Capture349.png)

    [![](img/b2b79bd5bf624c69ddc9768bf0a003e2.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200128161937/Capture350.png)

3.  **–version**: It will specify the version of jdeprscan.

    **输出:**

    ```java
    jdeprscan --version
    ```

    ```java
    9.0.4

    ```

    [![](img/d89dfe8de5eb097264db9cad9d904aab.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200128160201/Capture343.png)

4.  **–full-version**: It will print the version of the jdeprscan tool.

    **输出:**

    ```java
    jdeprscan --full-version
    ```

    ```java
    9.0.4+11

    ```

    [![](img/7d602f091ac944091aa6c1317b73c36c.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200128160321/Capture344.png)

5.  **–help**: It will display the help message for user. Instead of using -help, we can use -h also.

    **输出:**

    ```java
    jdeprscan --help
    ```

    [![](img/f14d62f178eef08c2d6c6d0cabc5a77f.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200128160639/Capture345.png)

6.  **–list**: It will list out the deprecated APIs. Instead of using -list, we can use -l also.

    **输出:**

    ```java
    jdeprscan --list
    ```

    [![](img/af77ef780949764a2a733bd4d2b57150.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200130155720/Capture352.png)

    [![](img/5a4d3b99326b9e6ee8467198bc7bc219.png)](https://media.geeksforgeeks.org/wp-content/uploads/20200130155838/Capture353.png)