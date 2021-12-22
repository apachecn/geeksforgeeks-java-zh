# Java 中的 AtomicLong lazySet()方法，带示例

> 原文:[https://www . geesforgeks . org/atomiclong-lazy set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-lazyset-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomic clong . lazy set()**是 Java 中的一个内置方法，它更新以前的值，并将其设置为一个新值，该值在参数中传递。

**语法:**

```java
public final void lazySet(long newVal)

```

**参数:**该功能接受一个需要更新的强制参数**新值**。

**返回值:**函数不返回任何内容。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the lazySet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val
            = new AtomicLong(0);

        System.out.println("Previous value: "
                           + val);

        val.lazySet(10);

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
// the lazySet() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicLong val = new AtomicLong(18);

        System.out.println("Previous value: "
                           + val);

        val.lazySet(200);

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

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomic clong . html # lazySet–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#lazySet--)