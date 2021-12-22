# Java 中的 LocalTime plusMinutes()方法，示例

> 原文:[https://www . geesforgeks . org/local time-plusminutes-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-plusminutes-method-in-java-with-examples/)

**LocalTime 类**的 **plusMinutes()** 方法用于将指定的分钟数值添加到该 LocalTime，并将结果作为 LocalTime 对象返回。这一瞬间是不可改变的。计算大约在午夜进行。

**语法:**

```java
public LocalTime plusMinutes(long MinutesToAdd)

```

**参数:**此方法接受单个参数**分钟添加**，即要添加的分钟值，可以是负值。

**返回值:**该方法返回一个基于该时间的**本地时间**，并加上分钟。

下面的程序说明了 plusMinutes()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.plusMinutes() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("19:34:50.63");

        // print LocalTime
        System.out.println("LocalTime before addition: "
                           + time);

        // add 55 Minutes using plusMinutes()
        LocalTime value = time.plusMinutes(55);

        // print result
        System.out.println("LocalTime after addition: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before addition: 19:34:50.630
LocalTime after addition: 20:29:50.630

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.plusMinutes() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("01:00:01");

        // print LocalTime
        System.out.println("LocalTime before addition: "
                           + time);

        // add -600 Minutes using plusMinutes()
        LocalTime value = time.plusMinutes(-600);

        // print result
        System.out.println("LocalTime after addition: "
                           + value);
    }
}
```

**输出:**

```java
LocalTime before addition: 01:00:01
LocalTime after addition: 15:00:01

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # plusMinutes(长)](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#plusMinutes(long))