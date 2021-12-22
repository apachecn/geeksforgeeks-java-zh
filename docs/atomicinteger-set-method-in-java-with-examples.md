# Java 中的 AtomicInteger set()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicintger-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicinteger-set-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicinteger . set()**是 Java 中的一个内置方法，它更新以前的值，并将其设置为一个新值，该值在参数中传递。

**语法:**

```java
public final void set(int newVal)

```

**参数:**该功能接受一个需要更新的强制参数**新值**。

**返回值:**函数不返回任何内容。

下面的程序演示了该功能:

**程序 1:**

```java
// Java program that demonstrates
// the set() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicInteger val
            = new AtomicInteger(0);

        System.out.println("Previous value: "
                           + val);

        val.set(10);

        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```java
Previous value: 0
Current value: 10

```

**程序二:**

```java
// Java program that demonstrates
// the set() function

import java.util.concurrent.atomic.AtomicInteger;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicInteger val
            = new AtomicInteger(18);

        System.out.println("Previous value: "
                           + val);

        val.set(200);

        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```java
Previous value: 18
Current value: 200

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicinteger . html # set–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicInteger.html#set--)