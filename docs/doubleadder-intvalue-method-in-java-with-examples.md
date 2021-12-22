# Java 中的 DoubleAdder intValue()方法，带示例

> 原文:[https://www . geesforgeks . org/double adder-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleadder-intvalue-method-in-java-with-examples/)

**java。DoubleAdder.intValue()** 是 java 中的一个内置方法，它在缩小原语转换后将 sum()作为 **int** 返回。创建类的对象时，其初始值为零。

**语法:**

```java
public int intValue()

```

**参数:**该方法不接受任何参数。

**返回值:**该方法将该对象表示的数值转换为 *int* 数据类型后返回。

以下程序说明了上述功能:

**程序 1** :

```java
// Program to demonstrate the intValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(11);
        num.add(10);

        // intValue operation on variable num
        num.intValue();

        // Print after intValue operation
        System.out.println("the value after intValue() is: " + num);
    }
}
```

**输出:**

```java
the value after intValue() is: 21.0

```

**程序二** :

```java
// Program to demonstrate the intValue() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(11);

        // intValue operation on variable num
        num.intValue();

        // Print after intValue operation
        System.out.println("the value after intValue() is: " + num);
    }
}
```

**输出:**

```java
the value after intValue() is: 11.0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/double adder . html # int value–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#intValue--)