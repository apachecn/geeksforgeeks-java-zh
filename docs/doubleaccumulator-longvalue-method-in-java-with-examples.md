# Java 中的 double 累加器 longValue()方法，带示例

> 原文:[https://www . geesforgeks . org/double 累加器-long value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleaccumulator-longvalue-method-in-java-with-examples/)

**Java。double 累加器. longValue()** 是 java 中的一个内置方法，它在缩小原语转换后将当前值作为 **long** 返回。这意味着初始数据类型是 double，它被显式转换为 long 类型。

**语法:**

```java
public long longValue()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法在缩小图元转换后将当前值作为 long 返回。

PBelow 程序说明了上述方法:

**程序 1:**

```java
// Java program to demonstrate the
// longValue() method

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

        // Print before longValue operation
        System.out.println("Old value is: "
                           + num);

        // Print after longValue operation
        System.out.println("Current long value is: "
                           + num.floatValue());
    }
}
```

**Output:**

```java
Old value is: 52.0
Current long value is: 52.0

```

**程序 2:**

```java
// Java program to demonstrate the
// longValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(26);
        num.accumulate(45);

        // Print before longValue operation
        System.out.println("Old value is: "
                           + num);

        // Print after longValue operation
        System.out.println("Current long value is: "
                           + num.floatValue());
    }
}
```

**Output:**

```java
Old value is: 71.0
Current long value is: 71.0

```