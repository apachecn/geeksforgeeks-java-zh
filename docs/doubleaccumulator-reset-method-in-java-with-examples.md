# Java 中的 double 累加器 reset()方法，示例

> 原文:[https://www . geeksforgeeks . org/double 累加器-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleaccumulator-reset-method-in-java-with-examples/)

**Java。double 累加器. reset()** 是 java 中的一个内置方法，用于重置变量，同时保持对标识值的更新。这意味着它只返回复位值，不接受任何参数。返回类型是 int。

**语法:**

```
public void reset()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法不返回任何内容。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program to demonstrate
// the reset() method

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

        // Print before doubleValue operation
        System.out.println("DoubleAccumulator before reset: "
                           + num);

        // resets current value
        num.reset();

        // Print after reset operation
        System.out.println("DoubleAccumulator after reset: "
                           + num);
    }
}
```

**Output:**

```
DoubleAccumulator before reset: 12.0
DoubleAccumulator after reset: 0.0

```

**程序 2:**

```
// Java program to demonstrate
// the reset() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(45);
        num.accumulate(17);

        // Print before doubleValue operation
        System.out.println("DoubleAccumulator before reset: "
                           + num);

        // resets current value
        num.reset();

        // Print after reset operation
        System.out.println("DoubleAccumulator after reset: "
                           + num);
    }
}
```

**Output:**

```
DoubleAccumulator before reset: 62.0
DoubleAccumulator after reset: 0.0

```