# Java 中 LongAdder doubleValue()方法，带示例

> 原文:[https://www . geesforgeks . org/long adder-double value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/longadder-doublevalue-method-in-java-with-examples/)

**Java 中的 LongAdder 类**创建一个初始和为零的新加法器。**爪哇。LongAdder.doubleValue()** 是 java 中的一个内置方法，它以双精度值的形式返回总和。创建类的对象时，其初始值为零。

**语法:**

```
public double doubleValue()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回一个**二进制值**，代表这个长加法器的和

以下程序演示了上述功能:

**程序 1:**

```
// Java program to demonstrate
// the LongAdder.doubleValue() method

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

        // doubleValue operation on num
        num.doubleValue();

        // Print after value
        System.out.println("Sum of LongAdder as double: "
                           + num);
    }
}
```

**Output:**

```
Initial value is: 0
After addition of 6, value is: 6
After addition of 5, value is: 11
Sum of LongAdder as double: 11

```

**程序 2:**

```
// Java program to demonstrate
// the LongAdder.doubleValue() method

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

        // doubleValue operation on num
        num.doubleValue();

        // Print after value
        System.out.println("Sum of LongAdder as double: "
                           + num);
    }
}
```

**Output:**

```
Initial value is: 0
After addition of 10, value is: 10
After addition of 100, value is: 110
Sum of LongAdder as double: 110

```