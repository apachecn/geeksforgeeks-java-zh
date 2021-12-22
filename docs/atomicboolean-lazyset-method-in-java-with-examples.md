# Java 中的 AtomicBoolean lazySet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicboolean-lazy set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicboolean-lazyset-method-in-java-with-examples/)

**java . util . concurrent . atomic . atomicboolean . lazy set()**是 Java 中的一个内置方法，它更新以前的值，并将其设置为一个新值，该值在参数中传递。

**语法:**

```
public final void lazySet(boolean newVal)

```

**参数:**该功能接受一个需要更新的强制参数**新值**。

**返回值:**函数不返回任何内容。

以下程序说明了上述功能:

**程序 1:**

```
// Java program that demonstrates
// the lazySet() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as false
        AtomicBoolean val
            = new AtomicBoolean(false);

        System.out.println("Previous value: "
                           + val);

        val.lazySet(true);

        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```
Previous value: false
Current value: true

```

**程序二:**

```
// Java program that demonstrates
// the lazySet() function

import java.util.concurrent.atomic.AtomicBoolean;

public class GFG {
    public static void main(String args[])
    {

        // Initially value as true
        AtomicBoolean val
            = new AtomicBoolean(true);

        System.out.println("Previous value: "
                           + val);

        val.lazySet(false);

        // Prints the updated value
        System.out.println("Current value: "
                           + val);
    }
}
```

**输出:**

```
Previous value: true
Current value: false

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicboolean . html # lazySet-boolean-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicBoolean.html#lazySet-boolean-)