# Java 中的 AtomicBoolean get()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicboolean-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicboolean-get-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomic Boolean . get()**是 Java 中的一个内置方法，它返回日期类型的布尔值的当前值。

**语法:**

```java
public final boolean get()

```

**参数:**函数不接受任何参数。

**返回值:**函数返回当前值

以下程序说明了上述功能:

**程序 1:**

```java
// Java Program to demonstrates
// the get() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as false
        AtomicBoolean val
            = new AtomicBoolean(false);

        // Gets the current value
        boolean res = val.get();

        System.out.println("current value: "
                           + res);
    }
}
```

**输出:**

```java
current value: false

```

程序二:

```java
// Java Program to demonstrates
// the get() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as true
        AtomicBoolean val = new AtomicBoolean(true);
        // Gets the current value
        boolean res = val.get();

        System.out.println("current value: "
                           + res);
    }
}
```

**输出:**

```java
current value: true

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicboolean . html # get–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicBoolean.html#get--)