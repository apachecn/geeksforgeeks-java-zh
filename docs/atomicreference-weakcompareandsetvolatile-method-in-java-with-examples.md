# Java 中的 atomic reference weakCompareAndSetVolatile()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomic reference-weakcompareandsetvolatile-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-weakcompareandsetvolatile-method-in-java-with-examples/)

如果当前值等于作为参数传递的预期值，则使用**原子引用**类的**weakCompareandsetvolatile()**方法自动将原子引用的值设置为新值。这个方法用 varhandle . weakcompareandset(Java . lang . object…)指定的内存效果更新这个值。如果向 AtomicRefrence 设置新值成功，则此方法返回 true。

**语法:**

```
public final boolean 
       weakCompareAndSetVolatile(V expectedValue,
                                 V newValue)

```

**参数:**该方法接受**期望值**为期望值，**新值**为新设定值。

**返回值:**此方法成功返回**真**。

下面的程序说明了 weakCompareAndSetVolatile()方法:
**程序 1:**

```
// Java program to demonstrate
// AtomicReference.weakCompareAndSetVolatile() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReference<Double> ref
            = new AtomicReference<Double>();

        // set some value
        ref.set(1234.00);

        // apply weakCompareAndSetVolatile()
        boolean result
            = ref.weakCompareAndSetVolatile(124.00,
                                            234.32);

        // print value
        System.out.println("Setting new value"
                           + " is successful = "
                           + result);

        System.out.println("Value = " + ref.get());
    }
}
```

**Output:**![](img/a793603317902be26bef42d685cd23ac.png)

**程序 2:**

```
// Java program to demonstrate
// AtomicReference.weakCompareAndSetVolatile() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object which stores String.
        AtomicReference<String> ref = new AtomicReference<String>();

        // set some value
        ref.set("GFG");

        // apply weakCompareAndSetVolatile()
        boolean result
            = ref.weakCompareAndSetVolatile(
                "GFG",
                "GEEKS FOR GEEKS");

        // print value
        System.out.println("Setting new value"
                           + " is successful = "
                           + result);
        System.out.println("Value  = " + ref.get());
    }
}
```

**Output:**![](img/eb67d886879377488fe4b6646499df4a.png)

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic reference . html # weakcomparendsetvolatile(V，V)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#weakCompareAndSetVolatile(V, V))