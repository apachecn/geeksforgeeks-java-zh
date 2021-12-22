# Java 中的 AtomicBoolean getAndSet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicboolean-getandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicboolean-getandset-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomicboolean . GetAnDset()**是 Java 中的一个内置方法，它将给定值设置为参数中传递的值，并在更新前返回数据类型为**布尔型**的值。

**语法:**

```java
public final boolean getAndSet(boolean val)

```

**参数:**该函数接受单个强制参数**值**，该值指定要更新的值。

**返回值:**该函数将执行更新操作前的值返回到前一个值。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the getAndSet() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as false
        AtomicBoolean val = new AtomicBoolean(false);

        // Updates and sets
        boolean res
            = val.getAndSet(true);

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
Previous value: false
Current value: true

```

**程序二:**

```java
// Java program that demonstrates
// the getAndSet() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as true
        AtomicBoolean val = new AtomicBoolean(true);

        // Gets and updates
        boolean res = val.getAndSet(false);

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
Previous value: true
Current value: false

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicboolean . html # getAndSet-boolean-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicBoolean.html#getAndSet-boolean-)