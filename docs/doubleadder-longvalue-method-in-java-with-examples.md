# Java 中的 DoubleAdder longValue()方法，带示例

> 原文:[https://www . geesforgeks . org/double adder-long value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleadder-longvalue-method-in-java-with-examples/)

**java。DoubleAdder.longValue()** 是 java 中的一个内置方法，它在缩小的原语转换后将 sum()作为 **long** 返回。创建类的对象时，其初始值为零。

**语法:**

```java
public long longValue()

```

**参数:**返回值:该方法将该对象表示的数值转换为*长*数据类型后返回。

下面的程序说明了上述方法:

**程序 1** :

```java
// Program to demonstrate the longValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {

        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(42);
        num.add(10);

        // longValue operation on variable num
        num.longValue();

        // Print after longValue operation
        System.out.println("the value after longValue() is: " + num);
    }
}
```

**输出:**

```java
the value after longValue() is: 52.0

```

**程序二** :

```java
// Program to demonstrate the longValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(62);

        // longValue operation on variable num
        num.longValue();

        // Print after longValue operation
        System.out.println("the value after longValue() is: " + num);
    }
}
```

**输出:**

```java
the value after longValue() is: 62.0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/double adder . html # longValue–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#longValue--)