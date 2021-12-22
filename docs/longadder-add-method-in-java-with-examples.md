# Java 中 LongAdder add()方法，带示例

> 原文:[https://www . geesforgeks . org/long adder-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longadder-add-method-in-java-with-examples/)

**Java 中的 LongAdder 类**创建一个初始和为零的新加法器。**爪哇。LongAdder.add()** 是 java 中的一个内置方法，用于添加给定值。

**语法:**

```
public void add(long x)

```

**参数:**该函数接受单个参数 **x** ，该参数指定要添加的值。

**返回值:**该方法不返回值。

以下程序演示了上述功能:

**程序 1:**

```
// Java program to demonstrate
// the LongAdder.add() method

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
    }
}
```

**Output:**

```
Initial value is: 0
After addition of 6, value is: 6
After addition of 5, value is: 11

```

**程序 2:**

```
// Java program to demonstrate
// the LongAdder.add() method

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

        // Add -5 to it
        num.add(-5);

        // Print the final value
        System.out.println("After addition"
                           + " of -5, value is: "
                           + num);
    }
}
```

**Output:**

```
Initial value is: 0
After addition of 10, value is: 10
After addition of -5, value is: 5

```