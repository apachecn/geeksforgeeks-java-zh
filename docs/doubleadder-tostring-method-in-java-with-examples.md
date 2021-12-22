# Java 中的 DoubleAdder toString()方法，带示例

> 原文:[https://www . geesforgeks . org/double adder-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleadder-tostring-method-in-java-with-examples/)

**java。DoubleAdder.toString()** 是 java 中的一个内置方法，返回 sum()方法的 String 表示形式。创建类的对象时，其初始值为零。

**语法:**

```
public String toString()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回总和的字符串表示形式。

下面的程序说明了上述方法:

**程序 1** :

```
// Program to demonstrate the toString() method

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
        System.out.println(" the value after sum() is: " + num);

        // toString operation on variable num
        num.toString();

        // Print after toString operation
        System.out.println("the value after toString() is: " + num);
    }
}
```

**输出:**

```
the value after sum() is: 52.0
the value after toString() is: 52.0

```

**程序二** :

```
// Program to demonstrate the toString() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(402);

        // sum operation on num
        num.sum();

        // Print after sum operation
        System.out.println(" the value after sum() is: " + num);

        // toString operation on variable num
        num.toString();

        // Print after toString operation
        System.out.println("the value after toString() is: " + num);
    }
}
```

**输出:**

```
the value after sum() is: 402.0
the value after toString() is: 402.0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/double adder . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#toString--)