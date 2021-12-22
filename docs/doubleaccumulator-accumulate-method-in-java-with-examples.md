# Java 中的 double 累加器累加()方法，示例

> 原文:[https://www . geeksforgeeks . org/double 累加器-grade-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleaccumulator-accumulate-method-in-java-with-examples/)

**Java。double 累加器. aggregate()**方法是 Java 中的一个内置方法，它用这个 double 累加器实例中的给定值进行更新。这意味着它将一个双精度值作为参数，并将其与调用它的 double 累加器实例相加。

**语法:**

```java
public void accumulate(double valueToBeAccumulated)

```

**参数:**此方法接受单个强制参数**值为累计**，这是要在此双累加器的当前实例中更新的双数值。

**返回值:**此方法不返回值。它只是更新这个双累加器。

下面的程序演示了该功能:

**程序 1:**

```java
// Java program to demonstrate
// the accumulate() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        // Create the DoubleAccumulator instance
        DoubleAccumulator num
            = new DoubleAccumulator(Double::sum,
                                    0L);

        // Print after accumulator
        System.out.println("Current DoubleAccumulator"
                           + " value is: "
                           + num);

        // Update 2 in this instance
        // using accumulate() method
        num.accumulate(2);

        // Print after accumulator
        System.out.println("Updated DoubleAccumulator"
                           + " value is: "
                           + num);
    }
}
```

**Output:**

```java
Current DoubleAccumulator value is: 0.0
Updated DoubleAccumulator value is: 2.0

```

**程序 2:**

```java
// Java program to demonstrate
// the accumulate() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        // Create the DoubleAccumulator instance
        DoubleAccumulator num
            = new DoubleAccumulator(Double::sum,
                                    0L);

        // Print after accumulator
        System.out.println("Current DoubleAccumulator"
                           + " value is: "
                           + num);

        // Update 42.2 in this instance
        // using accumulate() method
        num.accumulate(42.2);

        // Print after accumulator
        System.out.println("Updated DoubleAccumulator"
                           + " value is: "
                           + num);
    }
}
```

**Output:**

```java
Current DoubleAccumulator value is: 0.0
Updated DoubleAccumulator value is: 42.2

```