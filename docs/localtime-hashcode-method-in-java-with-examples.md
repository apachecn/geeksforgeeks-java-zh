# Java 中的 LocalTime hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/local time-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/localtime-hashcode-method-in-java-with-examples/)

一个**本地时间类**的 **hashCode()** 方法用于返回这个时间的 hashCode。如果对象没有改变，hashcode 总是相同的。Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希表、哈希表等哈希相关算法进行操作。也可以用对象的唯一代码(hashcode)来搜索对象。

**语法:**

```java
public int hashCode()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个**整数值**，它是 hashCode。

下面的程序说明了 hashCode()方法:

**程序 1:**

```java
// Java program to demonstrate
// LocalTime.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("10:44:59.73");

        // get nano second field using getNano()
        int hashcode = time.hashCode();

        // print result
        System.out.println("hashCode: "
                           + hashcode);
    }
}
```

**输出:**

```java
hashCode: 2074672050

```

**程序二:**

```java
// Java program to demonstrate
// LocalTime.hashCode() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {
        // create a LocalTime object
        LocalTime time
            = LocalTime.parse("18:00:01");

        // get nano second field using getNano()
        int hashcode = time.hashCode();

        // print result
        System.out.println("hashCode: "
                           + hashcode);
    }
}
```

**输出:**

```java
hashCode: -1466552081

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/localtime . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/java/time/LocalTime.html#hashCode())