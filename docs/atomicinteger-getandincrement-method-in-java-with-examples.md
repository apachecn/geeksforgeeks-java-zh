# Java 中的 AtomicInteger getAndIncrement()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-getandincrement-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-getandincrement-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicinteger . GetAnDicrement()**是 Java 中的一个内置方法，它将给定值增加 1，并在更新前返回数据类型为 **int** 的值。

**语法:**

```java
public final int getAndIncrement()

```

**参数:**函数不接受单个参数。

**返回值:**该函数将执行增量操作前的值返回到前一个值。

下面的程序演示了该功能:

**程序 1:**

```java
// Java program that demonstrates
// the getAndIncrement() function

import java.util.concurrent.atomic.AtomicInteger;
public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        // Decreases and gets
        // the previous value
        int res
            = val.getAndIncrement();

        System.out.println("Previous value: "
                           + res);

        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```java
Previous value: 0
Current value: 1

```

**程序二:**

```java
// Java program that demonstrates
// the getAndIncrement() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        // Increases 1 and gets
        // the previous value
        int res = val.getAndIncrement();

        System.out.println("Previous value: "
                           + res);
        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```java
Previous value: 18
Current value: 19

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html # getandinecrement–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#getAndIncrement--)