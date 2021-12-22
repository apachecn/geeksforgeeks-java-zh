# Java 中 LongAdder sum()方法，带示例

> 原文:[https://www . geesforgeks . org/long adder-sum-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longadder-sum-method-in-java-with-examples/)

**Java 中的 LongAdder 类**创建一个初始和为零的新加法器。**爪哇。LongAdder.sum()** 是 java 中一个返回总和的内置方法。

**语法:**

```java
public long sum()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回当前总和。

下面的程序演示了该功能:

以下程序演示了上述功能:

**程序 1:**

```java
// Java program to demonstrate
// the LongAdder.sum() method

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

        // sum operation on num
        num.sum();

        // Print after sum
        System.out.println("Returned sum value is: "
                           + num);
    }
}
```

**Output:**

```java
Initial value is: 0
After addition of 6, value is: 6
After addition of 5, value is: 11
Returned sum value is: 11

```

**程序 2:**

```java
// Java program to demonstrate
// the LongAdder.sum() method

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

        // sum operation on num
        num.sum();

        // Print after sum
        System.out.println("Returned sum value is: "
                           + num);
    }
}
```

**Output:**

```java
Initial value is: 0
After addition of 10, value is: 10
After addition of 100, value is: 110
Returned sum value is: 110

```