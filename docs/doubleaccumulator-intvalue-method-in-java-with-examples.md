# Java 中的 double 累加器 intValue()方法，示例

> 原文:[https://www . geesforgeks . org/double 累加器-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleaccumulator-intvalue-method-in-java-with-examples/)

**Java。double 累加器. intValue()** 是 java 中的一个内置方法，它在缩小原语转换后将当前值作为 **int** 返回。初始数据类型是 double，它被显式转换为 int 类型，不接受任何参数。

**语法:**

```
public int intValue()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法在收缩基元转换后将当前值作为 int 返回。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program to demonstrate
// intValue() method

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

        // Print before intValue operation
        System.out.println("Old value is: "
                           + num);

        // Print after intValue operation
        System.out.println("Current int value is: "
                           + num.intValue());
    }
}
```

**Output:**

```
Old value is: 52.0
Current int value is: 52

```

**程序 2:**

```
// Java program to demonstrate
// intValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(63);
        num.accumulate(1);

        // Print before intValue operation
        System.out.println("Old value is: "
                           + num);

        // Print after intValue operation
        System.out.println("Current int value is: "
                           + num.intValue());
    }
}
```

**Output:**

```
Old value is: 64.0
Current int value is: 64

```