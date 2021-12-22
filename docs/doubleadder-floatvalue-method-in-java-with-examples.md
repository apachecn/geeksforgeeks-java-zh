# Java 中的 DoubleAdder floatValue()方法，示例

> 原文:[https://www . geesforgeks . org/double adder-float value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleadder-floatvalue-method-in-java-with-examples/)

**java。DoubleAdder.floatValue()** 是 java 中的一个内置方法，它在缩小原语转换后将 sum()作为**浮点数**返回。创建类的对象时，其初始值为零。

**语法:**

```
public float floatValue()

```

**参数:**该方法不接受任何参数。

**返回值:**方法返回转换为浮点数据类型后该对象表示的数值。

下面的程序说明了上面的方法:

```
// Program to demonstrate the floatValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(11);
        num.add(10);

        // floatValue() operation on variable num
        num.floatValue();

        // Print after floatValue() operation
        System.out.println("the value after floatValue() is: " + num);
    }
}
```

**输出:**

```
the value after floatValue() is: 21.0

```

```
// Program to demonstrate the floatValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(10);

        // floatValue() operation on variable num
        num.floatValue();

        // Print after floatValue() operation
        System.out.println("the value after floatValue() is: " + num);
    }
}
```

**输出:**

```
the value after floatValue() is: 10.0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/double adder . html # float value–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#floatValue--)