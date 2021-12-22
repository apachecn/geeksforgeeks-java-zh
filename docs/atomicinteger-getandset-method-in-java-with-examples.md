# Java 中的 AtomicInteger getAndSet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-getandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-getandset-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicinteger . getandset()**是 Java 中的一个内置方法，它将给定值设置为参数中传递的值，并在更新前返回数据类型为 **int** 的值。

**语法:**

```
public final int getAndSet(int val)

```

**参数:**该函数接受单个强制参数**值**，该值指定要更新的值。

**返回值:**函数将执行更新操作前的值返回到前一个值。

下面的程序演示了该功能:

**程序 1:**

```
// Java program that demonstrates
// the getAndSet() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        // Updates and sets
        int res
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

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        // Gets and updates
        int res = val.getAndSet(12);

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

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicintger . html # getAndSet–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#getAndSet--)