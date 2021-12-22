# Java 中的 AtomicInteger longValue()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-long value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-longvalue-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicinteger . long value()**是 Java 中的一个内置方法，它通过将当前存储在对象中的值转换为长数据类型来返回该值，这是一种原语转换。

**语法:**

```
public int longValue()

```

**参数:**函数不接受单个参数。

**返回值:**函数以长数据类型返回当前值。

下面的程序演示了该功能:

**程序 1:**

```
// Java program that demonstrates
// the longValue() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        long res
            = val.longValue();

        // Prints the updated value
        System.out.println("Current value: "
                           + res);
    }
}
```

**输出:**

```
Current value: 0

```

**程序二:**

```
// Java program that demonstrates
// the longValue() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        long res = val.longValue();

        // Prints the updated value
        System.out.println("Current value: "
                           + res);
    }
}
```

**输出:**

```
Current value: 18

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html # longValue–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#longValue--)