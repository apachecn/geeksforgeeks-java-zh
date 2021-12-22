# Java 中的 AtomicLong intValue()方法，带示例

> 原文:[https://www . geesforgeks . org/atomiclong-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-intvalue-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomiclong . int value()**是 Java 中的一个内置方法，它通过执行一个缩小的原语转换来返回当前存储在数据类型为 **long** 的对象中的值。

**语法:**

```
public long intValue()

```

**参数:**函数不接受单个参数。

**返回值:**函数返回当前值。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program that demonstrates
// the intValue() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        long res
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

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

        long res = val.intValue();

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

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomiclong . html # int value–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#intValue--)