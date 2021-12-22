# 用示例在 Java 中原子克隆 getAndAdd()方法

> 原文:[https://www . geesforgeks . org/atomiclong-getandad-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-getandadd-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomic clong . GetAnDadd()**是 Java 中的一个内置方法，它将给定值加到当前值上，并在更新前返回数据类型为 **long** 的值。

**语法:**

```
public final long getAndAdd(long val)

```

**参数:**该函数接受单个强制参数**值**，该值指定要添加到当前值的值。

**返回值:**该函数返回对前一个值执行加法之前的值。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program that demonstrates
// the getAndAdd() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val = new AtomicLong(0);

        // Adds 7 and gets the previous value
        long res
            = val.getAndAdd(7);

        // Prints the updated value
        System.out.println("Previous value: "
                           + res);

        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```
Previous value: 0
Current value: 7

```

**程序二:**

```
// Java program that demonstrates
// the getAndAdd() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Adds 8 and gets the previous value
        long res = val.getAndAdd(8);

        // Prints the updated value
        System.out.println("Previous value: "
                           + res);

        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```
Previous value: 18
Previous value: 18
Current value: 26

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomic clong . html # getandad-long-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#getAndAdd-long-)