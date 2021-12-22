# Java 中的 DoubleAdder sum()方法，示例

> 原文:[https://www . geesforgeks . org/double adder-sum-in-Java-method-with-examples/](https://www.geeksforgeeks.org/doubleadder-sum-method-in-java-with-examples/)

**java。DoubleAdder.sum()** 是 java 中的一个内置方法，它返回当前的总和。创建类的对象时，其初始值为零。

**语法:**

```java
public double sum()

```

**参数:**该方法不接受任何参数。

**返回值:**此方法返回当前总和。

下面的程序说明了上述方法:

**程序 1** :

```java
// Program to demonstrate the sum() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(42);
        num.add(10);

        // sum operation on variable num
        num.sum();

        // Print after add operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出:**

```java
the current value is: 52.0

```

**程序二** :

```java
// Program to demonstrate the sum() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(10);

        // sum operation on variable num
        num.sum();

        // Print after add operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出:**

```java
the current value is: 10.0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/double adder . html # sum–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#sum--)