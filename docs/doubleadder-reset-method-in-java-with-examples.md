# Java 中的 DoubleAdder reset()方法，示例

> 原文:[https://www . geesforgeks . org/double adder-reset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleadder-reset-method-in-java-with-examples/)

**java。DoubleAdder.reset()** 是 java 中的一个内置方法，用于重置变量，保持总和为零。创建类的对象时，其初始值为零。

**语法:**

```
public void reset()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回复位值。

下面的程序说明了上述方法:

**程序 1** :

```
// Program to demonstrate the reset() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(42);
        num.add(10);

        // reset operation on variable num
        num.reset();

        // Print after add operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出:**

```
the current value is: 0.0

```

**程序二** :

```
// Program to demonstrate the reset() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(10);

        // reset operation on variable num
        num.reset();

        // Print after add operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出:**

```
the current value is: 0.0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/double adder . html # reset–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#reset--)