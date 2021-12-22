# Java 中的 AtomicLong getAndDecrement()方法，带示例

> 原文:[https://www . geesforgeks . org/atomiclong-getandreduction-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclong-getanddecrement-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomic clong . GetAndDefault()**是 Java 中的一个内置方法，它将给定值减少 1，并在更新前返回数据类型为 **long** 的值。

**语法:**

```java
public final long getAndDecrement()

```

**参数:**函数不接受单个参数。

**返回值:**该函数将执行减量操作前的值返回到前一个值。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the getAndDecrement() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 0
        AtomicLong val
            = new AtomicLong(0);

        // Decreases and gets
        // the previous value
        long res
            = val.getAndDecrement();

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
Current value: -1

```

**程序二:**

```java
// Java program that demonstrates
// the getAndDecrement() function

import java.util.concurrent.atomic.AtomicLong;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as 18
        AtomicLong val
            = new AtomicLong(18);

        // Decreases 1 and gets
        // the previous value
        long res = val.getAndDecrement();

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
Current value: 17

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomic clong . html # getanddecadel–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLong.html#getAndDecrement--)