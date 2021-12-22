# Java 中 LongAdder longValue()方法，带示例

> 原文:[https://www . geesforgeks . org/long adder-long value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/longadder-longvalue-method-in-java-with-examples/)

**Java 中的 LongAdder 类**创建一个初始和为零的新加法器。**爪哇。LongAdder.longValue()** 是 java 中的一个内置方法，返回 sum()。这个方法相当于 sum()方法。创建类的对象时，其初始值为零。

**语法:**

```
public long longValue()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回一个**长值**，即当前的和。

以下程序演示了上述功能:

**程序 1:**

```
// Java program to demonstrate
// the LongAdder.longValue() method

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

        // longValue operation on num
        num.longValue();

        // Print after sum
        System.out.println("Returned longValue is: "
                           + num);
    }
}
```

**Output:**

```
Initial value is: 0
After addition of 6, value is: 6
After addition of 5, value is: 11
Returned longValue is: 11

```

**程序 2:**

```
// Java program to demonstrate
// the LongAdder.longValue() method

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

        // longValue operation on num
        num.longValue();

        // Print after sum
        System.out.println("Returned longValue is: "
                           + num);
    }
}
```

**Output:**

```
Initial value is: 0
After addition of 10, value is: 10
After addition of 100, value is: 110
Returned longValue is: 110

```