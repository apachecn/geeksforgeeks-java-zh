# Java 中的 doubleValue 累加器 doubleValue()方法，示例

> 原文:[https://www . geesforgeks . org/double 累加器-double value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/doubleaccumulator-doublevalue-method-in-java-with-examples/)

**Java。double 累加器. doubleValue()** 是 java 中的一个内置方法，相当于 get()方法，它意味着只返回当前值，不取任何参数。此方法的返回类型是 int。

**语法:**

```java
public double doubleValue()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回 double 累加器实例的当前值。

下面的程序演示了该功能:

**程序 1:**

```java
// Java program to demonstrate the
// doubleValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(42);
        num.accumulate(10);

        // Print before doubleValue operation
        System.out.println("Old value is: "
                           + num);

        // Print after doubleValue operation
        System.out.println("Current double value is: "
                           + num.doubleValue());
    }
}
```

**Output:**

```java
Old value is: 52.0
Current double value is: 52.0

```

**程序 2:**

```java
// Java program to demonstrate the
// doubleValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(32);
        num.accumulate(45);

        // Print before doubleValue operation
        System.out.println("Old value is: "
                           + num);

        // Print after doubleValue operation
        System.out.println("Current double value is: "
                           + num.doubleValue());
    }
}
```

**Output:**

```java
Old value is: 77.0
Current double value is: 77.0

```