# Java 程序查找当前工作目录

> 原文:[https://www . geesforgeks . org/Java-program-to-find-current-working-directory/](https://www.geeksforgeeks.org/java-program-to-find-current-working-directory/)

Java 中系统类 中定义的 **getproperty()方法** ，用于检索参数列表中命名的属性值。此方法属性由接受参数的键指定。如果属性不存在，此版本的 getProperty 将返回 null。

**语法:**

```java
public static String getProperty(String key)

```

**参数:**

*   键:我们想要其系统属性的键

**返回:**

*   指定为键的系统属性
*   **空**:如果该键不存在属性。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Find 
// current working directory
import java.io.*;

public class GFG {

    public static void main(String[] args)
    {

        // Getting the path of system property
        String path = System.getProperty("user.dir");

        // Printing the path of the working Directory
        System.out.println("Working Directory = " + path);
    }
}
```

**输出:**

![](img/c453ba8d5da14d49011ffa70116317a2.png)