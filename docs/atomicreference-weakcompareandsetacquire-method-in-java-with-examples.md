# Java 中的原子引用 weakCompareAndSetAcquire()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomic reference-weakcompareandsetacquire-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-weakcompareandsetacquire-method-in-java-with-examples/)

如果当前值等于作为参数传递的预期值，则使用**原子引用**类的**weakCompareAndSetAcquire()**方法自动将原子引用的值设置为新值。此方法使用与 memory_order_acquire 排序兼容的内存排序效果来更新该值。如果向 AtomicRefrence 设置新值成功，则此方法返回 true。

**语法:**

```java
public final boolean
 weakCompareAndSetAcquire(V expectedValue,
                          V newValue)
```

**参数:**该方法接受**期望值**为期望值，**新值**为新设定值。
**返回值:**此方法成功返回真。

以下程序说明了 weakCompareAndSetAcquire()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// AtomicReference.weakCompareAndSetAcquire() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        // which stores Integer.
        AtomicReference<Long> ref
            = new AtomicReference<Long>();

        // set some value
        ref.set(11111111L);

        // apply weakCompareAndSetAcquire()
        boolean result
            = ref.weakCompareAndSetAcquire(
                1111111111111L,
                999999L);

        // print value
        System.out.println("Setting new value"
                           + " is successful = "
                           + result);
        System.out.println("Value = " + ref.get());
    }
}
```

**输出:**

![](img/26813345066febd1b100913a8b671137.png)

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// AtomicReference.weakCompareAndSetAcquire() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        // which stores String.
        AtomicReference<String> ref
            = new AtomicReference<String>();

        // set some value
        ref.set("WELCOME TO GEEKS FOR GEEKS");

        // apply weakCompareAndSetAcquire()
        boolean result
            = ref.weakCompareAndSetAcquire(
                "WELCOME TO GEEKS FOR GEEKS",
                "WELCOLME GEEKS");

        // print value
        System.out.println("Setting new value"
                           + " is successful = "
                           + result);
        System.out.println("Value  = " + ref.get());
    }
}
```

**输出:**

![](img/e4ea9699294b1d2f7202c744a83a6cd7.png)

**参考文献:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic reference . html # weakCompareAndSetAcquire(V，V)T4】