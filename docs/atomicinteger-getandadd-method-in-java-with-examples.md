# Java 中的 AtomicInteger getAndAdd()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-getandad-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-getandadd-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicinteger . GetAnDadd()**是 Java 中的一个内置方法，它将给定值加到当前值上，并在更新前返回数据类型为 **int** 的值。

**语法:**

```java
public final int getAndAdd(int val)

```

**参数:**该函数接受单个强制参数**值**，该值指定要添加到当前值的值。

**返回值:**该函数返回对前一个值执行加法之前的值。

下面的程序演示了该功能:

**程序 1:**

```java
// Java program that demonstrates
// the getAndAdd() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        // Adds 7 and gets the previous value
        int res
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

```java
Previous value: 0
Current value: 7

```

**程序二:**

```java
// Java program that demonstrates
// the getAndAdd() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        // Prints the updated value
        System.out.println("Previous value: "
                           + val);

        // Adds 8 and gets the previous value
        int res = val.getAndAdd(8);

        // Prints the updated value
        System.out.println("Previous value: "
                           + res);

        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```java
Previous value: 18
Previous value: 18
Current value: 26

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicintger . html # GetAnDadd-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#getAndAdd-int-)