# Java 中的 double 累加器 getThenReset()方法，示例

> 原文:[https://www . geesforgeks . org/double 累加器-getthenreset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleaccumulator-getthenreset-method-in-java-with-examples/)

**Java。double 累加器. getThenReset()** 是 java 中的一个内置方法，实际上相当于 get()后跟 Reset()。首先，它获取当前值，然后重置该值。复位值为零。返回类型是 int。

**语法:**

```
public double getThenReset()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回复位前的值。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program to demonstrate
// the getThenReset() method

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

        num.get();
        // before getThenReset the value is
        System.out.println("Old value is: "
                           + num);

        // getThenResets current value
        num.getThenReset();

        // Print after getThenReset operation
        System.out.println("Current value is: "
                           + num);
    }
}
```

**Output:**

```
Old value is: 52.0
Current value is: 0.0

```

**程序 2:**

```
// Java program to demonstrate
// the getThenReset() method import java.lang.*;

import java.util.concurrent.atomic.DoubleAccumulator;

public class GFG {
    public static void main(String args[])
    {

        DoubleAccumulator num
            = new DoubleAccumulator(
                Double::sum, 0L);

        // accumulate operation on num
        num.accumulate(74);
        num.accumulate(1);

        num.get();
        // before getThenReset the value is
        System.out.println("Old value is: "
                           + num);

        // getThenResets current value
        num.getThenReset();

        // Print after getThenReset operation
        System.out.println("Current value is: "
                           + num);
    }
}
```

**Output:**

```
Old value is: 75.0
Current value is: 0.0

```