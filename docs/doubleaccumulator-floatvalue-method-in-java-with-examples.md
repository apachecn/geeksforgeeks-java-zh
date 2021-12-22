# Java 中的 double 累加器 floatValue()方法，示例

> 原文:[https://www . geesforgeks . org/double 累加器-float value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleaccumulator-floatvalue-method-in-java-with-examples/)

**Java。double 累加器. floatValue()** 是 java 中的一个内置方法，它在缩小原语转换后将当前值作为**浮点**返回。这意味着初始数据类型是 double，它被显式转换为 float 类型。

**语法:**

```java
public float floatValue()

```

**参数:**函数不接受任何参数。

**返回值:**方法返回转换为类型 float 后该对象表示的数值。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program to demonstrate the
// floatValue() method

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

        // Print before floatValue operation
        System.out.println("Old value is: "
                           + num);

        // Print after floatValue operation
        System.out.println("Current float value is: "
                           + num.floatValue());
    }
}
```

**Output:**

```java
Old value is: 52.0
Current float value is: 52.0

```

**程序 2:**

```java
// Java program to demonstrate the
// floatValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(7);
        num.accumulate(85);

        // Print before floatValue operation
        System.out.println("Old value is: "
                           + num);

        // Print after floatValue operation
        System.out.println("Current float value is: "
                           + num.floatValue());
    }
}
```

**Output:**

```java
Old value is: 92.0
Current float value is: 92.0

```