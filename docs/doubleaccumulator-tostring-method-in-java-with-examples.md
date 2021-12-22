# Java 中的 double 累加器 toString()方法，示例

> 原文:[https://www . geesforgeks . org/double 累加器-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleaccumulator-tostring-method-in-java-with-examples/)

**Java。double 累加器. toString()** 是 java 中的一个内置方法，返回当前值的 String 表示形式。数值被显式转换为初始数据类型为双精度的字符串。

**语法:**

```java
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回当前值的字符串表示形式。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program to demonstrate
// the toString() method

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

        // before toString the value is
        System.out.println("DoubleAccumulator: "
                           + num.get());

        // Print String representation
        System.out.println("String representation: "
                           + num.toString());
    }
}
```

**Output:**

```java
DoubleAccumulator: 52.0
String representation: 52.0

```

**程序 2:**

```java
// Java program to demonstrate
// the toString() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {
        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(75);
        num.accumulate(1);

        // before toString the value is
        System.out.println("DoubleAccumulator: "
                           + num.get());

        // Print String representation
        System.out.println("String representation: "
                           + num.toString());
    }
}
```

**Output:**

```java
DoubleAccumulator: 76.0
String representation: 76.0

```