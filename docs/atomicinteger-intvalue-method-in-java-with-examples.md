# Java 中的 AtomicInteger intValue()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicinteger-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-intvalue-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicinteger . int value()**是 Java 中的一个内置方法，它返回当前存储在数据类型为 **int** 的对象中的值。

**语法:**

```
public int intValue()

```

**参数:**函数不接受单个参数。

**返回值:**函数返回当前值。

下面的程序演示了该功能:

**程序 1:**

```
// Java program that demonstrates
// the intValue() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        int res
            = val.intValue();

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
// the intValue() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        int res = val.intValue();

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

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html # intValue–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#intValue--)