# Java 中的 Instant equals()方法，示例

> 原文:[https://www . geesforgeks . org/instant-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/instant-equals-method-in-java-with-examples/)

**即时类**的**等于(对象其他即时)**方法用于将此即时与作为参数传递的即时对象进行比较。两个实例之间的比较是基于时刻的时间线位置。该方法返回的值确定如下:

*   Returns true if two instances are equal.
*   If the two instances are not equal, false is returned.

**语法:**

```java
public boolean equals(Object otherInstant)
```

**参数:**该方法接受一个强制参数 **otherInstant** ，即需要比较的另一个时刻，不应该为空。

**返回值:**该方法返回一个布尔值，如下所示:

*   **真**:如果两个实例相等。
*   **false** :如果两个实例不相等。

下面的程序说明了 Instant.equals()方法:

**程序 1:** 当两个实例相等时

```java
// Java program to demonstrate
// Instant.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two instance objects
        Instant instant1
            = Instant.parse("2018-10-20T16:55:30.00Z");

        Instant instant2
            = Instant.parse("2018-10-20T16:55:30.00Z");

        // print Instant Values
        System.out.println("Instant1: "
                           + instant1);
        System.out.println("Instant2: "
                           + instant2);

        // compare both instant
        boolean value = instant1.equals(instant2);

        // print results
        System.out.println("Are both instants are equal: "
                           + value);
    }
}
```

**输出:**

```java
Instant1: 2018-10-20T16:55:30Z
Instant2: 2018-10-20T16:55:30Z
Are both instants are equal: true

```

**程序 2:** 当两个实例不相等时

```java
// Java program to demonstrate
// Instant.equals() method

import java.time.*;

public class GFG {
    public static void main(String[] args)
    {

        // create two instance objects
        Instant instant1
            = Instant.parse("2018-10-20T16:55:30.00Z");

        Instant instant2
            = Instant.parse("2011-10-20T16:55:30.00Z");

        // print Instant Values
        System.out.println("Instant1: "
                           + instant1);
        System.out.println("Instant2: "
                           + instant2);

        // compare both instant
        boolean value = instant1.equals(instant2);

        // print results
        System.out.println("Are both instants are equal: "
                           + value);
    }
}
```

**输出:**

```java
Instant1: 2018-10-20T16:55:30Z
Instant2: 2011-10-20T16:55:30Z
Are both instants are equal: false

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/instant . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/Instant.html#equals(java.lang.Object))