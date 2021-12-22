# Java 中的 double 累加器 get()方法，示例

> 原文:[https://www . geesforgeks . org/double 累加器-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleaccumulator-get-method-in-java-with-examples/)

**Java。double 累加器. get()** 方法是 Java 中的一个内置方法，在这个 double 累加器实例中返回当前值。这意味着它只返回当前值，不接受任何参数。返回类型是 int。

**语法:**

```
public double get()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回 double 累加器对象的当前值。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program to demonstrate
// the get() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(2);
        num.accumulate(10);

        // Gets current value
        double x = num.get();

        // Print after get operation
        System.out.println("Current value is: "
                           + x);
    }
}
```

**Output:**

```
Current value is: 12.0

```

**程序 2:**

```
// Java program to demonstrate
// the get() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(24);
        num.accumulate(1);

        // Gets current value
        double x = num.get();

        // Print after get operation
        System.out.println("Current value is: "
                           + x);
    }
}
```

**Output:**

```
Current value is: 25.0

```