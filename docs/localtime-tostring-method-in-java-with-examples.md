# Java 中的 LocalTime toString()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-tostring-method-in-java-with-examples/)

**LocalTime 类**的 **toString()** 方法用于将该时间表示为字符串，如 20:15:34.111。

以下 ISO-8601 格式用于表示:

*   HH:毫米:ss .嘘！嘘

此方法从对象类派生而来，其行为方式类似。

**语法:**

```java
public String toString()

```

**参数:**该方法不接受参数。

**返回值:**该方法返回该本地时间的**字符串表示**。

下面的程序说明了 toString()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // print LocalTime
        System.out.println("LocalTime : "
                           + time.toString());
    }
}
```

**输出:**

```java
LocalTime : 19:34:50.630

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.toString() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:00:01");

        // print LocalTime
        System.out.println("Old LocalTime: "
                           + time.toString());

        // add 600 Minutes using plusMinutes()
        LocalTime value = time.plusMinutes(600);

        // print result
        System.out.println("New LocalTime: "
                           + value.toString());
    }
}
```

**输出:**

```java
Old LocalTime: 01:00:01
New LocalTime: 11:00:01

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#toString())