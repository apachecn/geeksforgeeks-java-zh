# Java 中的 LocalDate toString()方法，带示例

> 原文:[https://www . geesforgeks . org/local date-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localdate-tostring-method-in-java-with-examples/)

一个 **LocalDate** 类的 **toString()** 方法用于将该日期作为字符串获取，如 2019-01-01。输出将采用 ISO-8601 格式。

**语法:**

```java
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回表示该日期的**字符串**，不为空。

下面的程序说明了 toString()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalDate.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate localD
            = LocalDate.parse("2018-12-06");

        // print LocalDate
        System.out.println("LocalDate: "
                           + localD.toString());
    }
}
```

**输出:**

```java
LocalDate: 2018-12-06

```

**程序二:**

```java
// Java program to demonstrate
// LocalDate.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalDate object
        LocalDate localD
            = LocalDate.parse("2021-06-30");

        // print LocalDate
        System.out.println("LocalDate: "
                           + localD.toString());
    }
}
```

**输出:**

```java
LocalDate: 2021-06-30

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/local date . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalDate.html#toString())