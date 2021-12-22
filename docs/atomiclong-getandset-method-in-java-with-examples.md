# Java 中的 AtomicLong getAndSet()方法，带示例

> 原文:[https://www . geesforgeks . org/atomiclong-getandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-getandset-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomiclong . getandset()**是 Java 中的一个内置方法，它将给定值设置为参数中传递的值，并在更新前返回数据类型为 **long** 的值。

**语法:**

```
public final long getAndSet(long val)

```

**参数:**该函数接受单个强制参数**值**，该值指定要更新的值。

**返回值:**函数将执行更新操作前的值返回到前一个值。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program that demonstrates
// the getAndSet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        // Updates and sets
        long res
            = val.getAndSet(10);

        System.out.println("Previous value: "
                           + res);

        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```
Previous value: 0
Current value: 10

```

**程序二:**

```
// Java program that demonstrates
// the getAndSet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

        // Gets and updates
        long res = val.getAndSet(12);

        System.out.println("Previous value: "
                           + res);
        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```
Previous value: 18
Current value: 12

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomic clong . html # getAndSet–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#getAndSet--)