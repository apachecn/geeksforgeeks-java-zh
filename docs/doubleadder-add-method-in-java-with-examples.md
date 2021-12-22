# Java 中的 DoubleAdder add()方法，示例

> 原文:[https://www . geesforgeks . org/double adder-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doubleadder-add-method-in-java-with-examples/)

**java。DoubleAdder.add()** 是 java 中的一个内置方法，它将给定的值添加到先前的值或初始值中。创建类的对象时，其初始值为零。

**语法:**

```java
public void add(double x)

```

**参数:**此方法接受单个参数 **x** ，指定要添加的值。

**返回值:**该方法返回加法运算后的新值。

以下程序说明了上述功能:

**程序 1** :

```java
// Program to demonstrate the add() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(42);
        num.add(10);

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
// Program to demonstrate the add() method

import java.lang.*;
import java.util.concurrent.atomic.DoubleAdder;

public class GFG {
    public static void main(String args[])
    {
        DoubleAdder num = new DoubleAdder();

        // add operation on num
        num.add(1);

        // Print after add operation
        System.out.println(" the current value is: " + num);
    }
}
```

**输出:**

```java
the current value is: 1.0

```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/double adder . html # add-double-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/DoubleAdder.html#add-double-)