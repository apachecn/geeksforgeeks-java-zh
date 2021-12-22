# Java 中 LongAdder increment()方法，带示例

> 原文:[https://www . geesforgeks . org/long adder-increment-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longadder-increment-method-in-java-with-examples/)

**Java 中的 LongAdder 类**创建一个初始和为零的新加法器。**爪哇。LongAdder.increment()** 是 java 中的一个内置方法，将值增加 1。

**语法:**

```
public void increment()

```

**参数:**函数不接受任何参数。

**返回值:**该方法不返回值。

以下程序演示了上述功能:

**程序 1:**

```
// Java program to demonstrate
// the LongAdder.increment() method

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

        // Increment operation on num
        num.increment();

        // Print after increment
        System.out.println("After increment, "
                           + " value is: "
                           + num);
    }
}
```

**Output:**

```
Initial value is: 0
After addition of 6, value is: 6
After increment,  value is: 7

```

**程序 2:**

```
// Java program to demonstrate
// the LongAdder.increment() method

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

        // Increment operation on num
        num.increment();

        // Print after increment
        System.out.println("After increment, "
                           + " value is: "
                           + num);
    }
}
```

**Output:**

```
Initial value is: 0
After addition of 10, value is: 10
After increment,  value is: 11

```