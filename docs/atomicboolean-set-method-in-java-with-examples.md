# Java 中的 AtomicBoolean set()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicboolean-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicboolean-set-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicboolean . set()**是 Java 中的一个内置方法，它更新以前的值，并将其设置为一个新值，该值在参数中传递。

**语法:**

```java
public final void set(boolean newVal)

```

**参数:**该功能接受一个需要更新的强制参数**新值**。

**返回值:**函数不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```java
// Java program that demonstrates
// the set() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as false
        AtomicBoolean val
            = new AtomicBoolean(false);

        System.out.println("Previous value: "
                           + val);

        val.set(true);

        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```java
Previous value: false
Current value: true

```

**程序二:**

```java
// Java program that demonstrates
// the set() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as true
        AtomicBoolean val
            = new AtomicBoolean(true);

        System.out.println("Previous value: "
                           + val);

        val.set(false);

        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```java
Previous value: true
Current value: false

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicboolean . html # set-boolean-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicBoolean.html#set-boolean-)