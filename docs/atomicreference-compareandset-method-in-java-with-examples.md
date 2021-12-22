# Java 中的 AtomicReference compareAndSet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomic reference-compareandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-compareandset-method-in-java-with-examples/)

一个**原子引用**类的 **compareAndSet()** 方法用于将原子引用对象的值自动设置为新值，如果原子引用对象的当前值等于预期值，则返回真，如果操作成功，则返回假。此方法使用设置的内存语义更新值，就像变量被声明为 volatile 一样。

**语法:**

```java
public final V compareAndSet(V expectedValue,
                             V newValue)

```

**参数:**该方法接受**期望值**为期望值，**新值**为新设定值。

**返回值:**该方法返回**见证值**，如果成功则与期望值相同。

下面的程序说明了 compareAndSet()方法:
**程序 1:**

```java
// Java program to demonstrate
// AtomicReference.compareAndSet() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReference<Long> ref
            = new AtomicReference<Long>();

        // set some value
        ref.set(987654321L);

        // apply compareAndSet()
        boolean response
            = ref.compareAndSet(1234L,
                                999999L);

        // print value
        System.out.println(" Value is set = "
                           + response);
    }
}
```

**Output:**

```java
Value is set = false

```

**程序 2:**

```java
// Java program to demonstrate
// AtomicReference.compareAndSet() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReference<String> ref
            = new AtomicReference<String>();

        // set some value
        ref.set("Geeks For Geeks");

        // apply compareAndSet()
        boolean response
            = ref.compareAndSet(
                "Geeks For Geeks",
                "GFG");

        // print value
        System.out.println(" Value is set = "
                           + response);
    }
}
```

**Output:**

```java
Value is set = true

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic reference . html # compareAndSet(V，V)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#compareAndSet(V, V))