# Java 中的 AtomicReferenceArray weakCompareAndSetVolatile()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicreferencearray-weakcompareandsetvolatile-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-weakcompareandsetvolatile-method-in-java-with-examples/)

一个**原子引用数组**类的**WeakCompareandSetvolatile()**方法用于在当前值等于作为参数传递的预期值的情况下，自动将索引 I 处的元素值设置为原子引用数组的新值到新值。这个方法用 varhandle . weakcompareandset(Java . lang . object…)指定的内存效果更新这个值。如果向 AtomicRefrence 设置新值成功，则此方法返回 true。

**语法:**

```java
public final boolean
       weakCompareAndSetVolatile(int i,
                                 E expectedValue,
                                 E newValue)

```

**参数:**该方法接受 **i** 作为原子引用数组的索引来执行操作，**期望值**是期望值，**新值**是要设置的新值。

**返回值:**如果成功，该方法返回 true。

下面的程序说明了 weakCompareAndSetVolatile()方法:
**程序 1:**

```java
// Java program to demonstrate AtomicReferenceArray
// weakCompareAndSetVolatile() method

import java.util.concurrent.atomic.AtomicReferenceArray;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReferenceArray<Double> ref
            = new AtomicReferenceArray<Double>(5);

        // set some value
        ref.set(1, 1234.00);
        ref.set(0, 2234.00);
        ref.set(2, 3234.00);

        // apply weakCompareAndSetVolatile()
        boolean result
            = ref.weakCompareAndSetVolatile(1, 124.00,
                                            234.32);

        // print value
        System.out.println("Setting new value"
                           + " is successful = "
                           + result);

        System.out.println("Value of index 1 = "
                           + ref.get(1));
    }
}
```

**Output:**![](img/d39142ae1c73b0d2408ae3f14dc858ea.png)

**程序 2:**

```java
// Java program to demonstrate AtomicReferenceArray
// weakCompareAndSetVolatile() method

import java.util.concurrent.atomic.AtomicReferenceArray;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReferenceArray<String> ref
            = new AtomicReferenceArray<String>(5);

        // set some value
        ref.set(0, "AMANDIP");
        ref.set(1, "AMAN");

        // apply weakCompareAndSetVolatile()
        boolean result
            = ref.weakCompareAndSetVolatile(
                0,
                "AMARDIP",
                "AMAR");

        // print value
        System.out.println("Setting new value"
                           + " is successful = "
                           + result);

        System.out.println("Value of index 0 = "
                           + ref.get(0));
    }
}
```

**Output:**![](img/d3b6cb0f17cf1681e348894112074e3d.png)

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic referencearray . html # weakCompareAndSetVolatile(V，V)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#weakCompareAndSetVolatile(V, V))