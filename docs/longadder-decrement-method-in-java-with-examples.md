# Java 中 LongAdder 减量()方法，示例

> 原文:[https://www . geesforgeks . org/long adder-减量-Java-in-method-with-examples/](https://www.geeksforgeeks.org/longadder-decrement-method-in-java-with-examples/)

**Java 中的 LongAdder 类**创建一个初始和为零的新加法器。**爪哇。long adder . decade()**是 java 中的一个内置方法，可以将该值减少 1。

**语法:**

```java
public void decrement()

```

**参数:**函数不接受任何参数。

**返回值:**该方法不返回值。

以下程序演示了上述功能:

**程序 1:**

```java
// Java program to demonstrate
// the LongAdder.decrement() method

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

        // Print the new value
        System.out.println("After addition"
                           + " of 6, value is: "
                           + num);

        // decrement operation on num
        num.decrement();

        // Print after decrement
        System.out.println("After decrement, "
                           + " value is: "
                           + num);
    }
}
```

**Output:**

```java
Initial value is: 0
After addition of 6, value is: 6
After decrement,  value is: 5

```

**程序 2:**

```java
// Java program to demonstrate
// the LongAdder.decrement() method

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

        // Print the new value
        System.out.println("After addition"
                           + " of 10, value is: "
                           + num);

        // decrement operation on num
        num.decrement();

        // Print after decrement
        System.out.println("After decrement, "
                           + " value is: "
                           + num);
    }
}
```

**Output:**

```java
Initial value is: 0
After addition of 10, value is: 10
After decrement,  value is: 9

```