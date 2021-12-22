# Java 中的 DoubleAdder doubleValue()方法，示例

> 原文:[https://www . geesforgeks . org/double adder-double value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/doubleadder-doublevalue-method-in-java-with-examples/)

**java。DoubleAdder.doubleValue()** 是 java 中的一个内置方法，相当于方法 sum()，也就是说它返回当前的 sum 值。创建类的对象时，其初始值为零。

**语法:**

```
public double doubleValue()

```

**参数:**该方法不接受任何参数。

**返回值:**此方法返回当前总和。

下面的程序说明了上述方法:

**程序 1** :

```
// Program to demonstrate the doubleValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(42);
        num.add(10);

        // doubleValue operation on variable num
        num.doubleValue();

        // Print after doubleValue operation
        System.out.println("the value after doubleValue() is: " + num);
    }
}
```

**输出:**

```
the value after doubleValue() is: 52.0

```

**程序二** :

```
// Program to demonstrate the doubleValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(72);

        // doubleValue operation on variable num
        num.doubleValue();

        // Print after doubleValue operation
        System.out.println("the value after doubleValue() is: " + num);
    }
}
```

**输出:**

```
the value after doubleValue() is: 72.0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/double adder . html # double value–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#doubleValue--)