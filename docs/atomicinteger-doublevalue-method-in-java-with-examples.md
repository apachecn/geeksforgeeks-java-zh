# Java 中的 AtomicInteger doubleValue()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicinteger-double value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/atomicinteger-doublevalue-method-in-java-with-examples/)

**java . util . concurrent . atomic . AtomicInteger . Double value()**是 Java 中的一个内置方法，它在执行原语转换后，将 AtomicInteger 的当前值作为 **Double** 数据类型返回。

**语法:**

```java
public double doubleValue()

```

**参数:**函数不接受任何参数。

**返回值:**该函数返回转换为 double 类型后该对象表示的数值。

下面的程序演示了该功能:

**程序 1:**

```java
// Java Program to demonstrates
// the doubleValue() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        val.addAndGet(7);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Gets the double value
        double res = val.doubleValue();

        System.out.println("Double value: "
                           + res);
    }
}
```

**输出:**

```java
Previous value: 7
Double value: 7.0

```

```java
// Java Program to demonstrates
// the doubleValue() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        val.addAndGet(7);

        // Gets the double value
        System.out.println("Previous value: "
                           + val);

        // Decreases the value by 1
        double res = val.doubleValue();

        System.out.println("Double value: "
                           + res);
    }
}
```

**输出:**

```java
Previous value: 25
Double value: 25.0

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html # double value–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#doubleValue--)