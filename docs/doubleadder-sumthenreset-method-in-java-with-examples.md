# Java 中的 DoubleAdder sumThenReset()方法，示例

> 原文:[https://www . geesforgeks . org/double adder-sumthenreset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleadder-sumthenreset-method-in-java-with-examples/)

**java。DoubleAdder.sumThenReset()** 是 java 中的一个内置方法，相当于 sum()然后 Reset()方法，即首先计算有效的和，然后重置值，以保持值为零。创建类的对象时，其初始值为零。

**语法:**

```
public double sumThenReset()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回总和。

下面的程序说明了上述方法:

**程序 1** :

```
// Program to demonstrate the sumThenReset() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(42);
        num.add(10);

        // sum operation on num
        num.sum();

        // Print after sum operation
        System.out.println(" the value after sum is: " + num);

        // sumThenReset operation on variable num
        num.sumThenReset();

        // Print after sumThenReset operation
        System.out.println("the current value is: " + num);
    }
}
```

**输出:**

```
the value after sum is: 52.0
the current value is: 0.0

```

**程序二** :

```
// Program to demonstrate the sumThenReset() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(254);

        // sum operation on num
        num.sum();

        // Print after sum operation
        System.out.println(" the value after sum is: " + num);

        // sumThenReset operation on variable num
        num.sumThenReset();

        // Print after sumThenReset operation
        System.out.println("the current value is: " + num);
    }
}
```

**输出:**

```
the value after sum is: 254.0
the current value is: 0.0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/double adder . html # sumthereset–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#sumThenReset--)