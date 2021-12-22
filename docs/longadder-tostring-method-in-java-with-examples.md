# Java 中的 LongAdder toString()方法，带示例

> 原文:[https://www . geesforgeks . org/long adder-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longadder-tostring-method-in-java-with-examples/)

**Java 中的 LongAdder 类**创建一个初始和为零的新加法器。**爪哇。LongAdder.toString()** 是 Java 中的一个内置方法，返回这个 LongAdder 的 String 表示。创建类的对象时，其初始值为零。

**语法:**

```java
public String toString()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回一个**字符串值**，它是这个长加法器的字符串表示。

以下程序演示了上述功能:

**程序 1:**

```java
// Java program to demonstrate
// the LongAdder.toString() method

import java.lang.*;
import java.util.concurrent.atomic.LongAdder;

public class GFG {
    public static void main(String args[])
    {

        // Initialized with 0
        LongAdder num = new LongAdder();

        // Print the initial value
        System.out.println("Initial value is: "
                           + num);

        // Add 6 to it
        num.add(6);

        // Print the final value
        System.out.println("After addition"
                           + " of 6, value is: "
                           + num);

        // Add 5 to it
        num.add(5);

        // Print the final value
        System.out.println("After addition"
                           + " of 5, value is: "
                           + num);

        // toString operation on num
        System.out.println("String representation"
                           + " of the LongAdder: "
                           + num.toString());
    }
}
```

**Output:**

```java
Initial value is: 0
After addition of 6, value is: 6
After addition of 5, value is: 11
String representation of the LongAdder: 11

```

**程序 2:**

```java
// Java program to demonstrate
// the LongAdder.toString() method

import java.lang.*;
import java.util.concurrent.atomic.LongAdder;

public class GFG {
    public static void main(String args[])
    {

        // Initialized with 0
        LongAdder num = new LongAdder();

        // Print the initial value
        System.out.println("Initial value is: "
                           + num);

        // Add 10 to it
        num.add(10);

        // Print the final value
        System.out.println("After addition"
                           + " of 10, value is: "
                           + num);

        // Add 100 to it
        num.add(100);

        // Print the final value
        System.out.println("After addition"
                           + " of 100, value is: "
                           + num);

        // toString operation on num
        System.out.println("String representation"
                           + " of the LongAdder: "
                           + num.toString());
    }
}
```

**Output:**

```java
Initial value is: 0
After addition of 10, value is: 10
After addition of 100, value is: 110
String representation of the LongAdder: 110

```