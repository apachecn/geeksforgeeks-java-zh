# Java 中的 LongAdder sumThenReset()方法，带示例

> 原文:[https://www . geesforgeks . org/long adder-sumthenreset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longadder-sumthenreset-method-in-java-with-examples/)

**Java 中的 LongAdder 类**创建一个初始和为零的新加法器。**爪哇。LongAdder.sumThenReset()** 是 Java 中的一个内置方法，相当于 sum()然后 Reset()函数。首先，计算总和，然后将其重置为值 0。创建类的对象时，其初始值为零。

**语法:**

```java
public long sumThenReset()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回**一个长值**，该长值是该长加法器重置为 0 之前的当前总和。

以下程序演示了上述功能:

**程序 1:**

```java
// Java program to demonstrate
// the LongAdder.sumThenReset() method

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

        // sumThenReset operation on num
        System.out.println("Returned sum before reset: "
                           + num.sumThenReset());

        // Print the current value
        System.out.println("Current value is: "
                           + num);
    }
}
```

**Output:**

```java
Initial value is: 0
After addition of 6, value is: 6
After addition of 5, value is: 11
Returned sum before reset: 11
Current value is: 0

```

**程序 2:**

```java
// Java program to demonstrate
// the LongAdder.sumThenReset() method

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

        // sumThenReset operation on num
        System.out.println("Returned sum before reset: "
                           + num.sumThenReset());

        // Print the current value
        System.out.println("Current value is: "
                           + num);
    }
}
```

**Output:**

```java
Initial value is: 0
After addition of 10, value is: 10
After addition of 100, value is: 110
Returned sum before reset: 110
Current value is: 0

```