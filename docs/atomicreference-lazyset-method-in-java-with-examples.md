# Java 中的 AtomicReference lazySet()方法，带示例

> 原文:[https://www . geesforgeks . org/atomicreference-lazy set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-lazyset-method-in-java-with-examples/)

一个**原子引用**类的 **lazySet()** 方法用于设置这个原子引用对象的值，该对象具有由 VarHandle . SetRelease(Java . lang . object…)指定的内存效果，以确保先前的加载和存储在这次访问后不会被重新排序。

**语法:**

```java
public final void lazySet(V newValue)

```

**参数:**此方法接受新值，即要设置的新值。

**返回值:**此方法不返回任何内容。

下面的程序说明了 lazySet()方法:
**程序 1:**

```java
// Java program to demonstrate
// AtomicReference.lazySet() method
import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReference<Integer> ref
            = new AtomicReference<Integer>();

        // set some value using lazySet method
        ref.lazySet(67545678);

        // print value
        System.out.println("Integer value = "
                           + ref.get());
    }
}
```

**Output:**

```java
Integer value = 67545678

```

**程序 2:**

```java
// Java program to demonstrate
// AtomicReference.lazySet() method
import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        AtomicReference<String> ref
            = new AtomicReference<String>();

        // set some value using lazySet()
        ref.lazySet("GFG(GeeksForGeeks)");

        // print value
        System.out.println(ref.get());
    }
}
```

**Output:**

```java
GFG(GeeksForGeeks)

```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic reference . html # lazySet(V)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#lazySet(V))