# Java 中的原子引用 weakCompareAndSet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomic reference-weakcompareandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreference-weakcompareandset-method-in-java-with-examples/)

如果当前值等于作为参数传递的预期值，则使用**原子引用**类的 **weakCompareAndSet()** 方法自动将原子引用的值设置为新值。此方法使用内存读取语义更新值，就像变量被声明为可变类型的变量一样。如果向原子引用设置新值成功，则此方法返回 true。

**语法:**

```java
public final boolean weakCompareAndSet(V expectedValue,
                                       V newValue)

```

**参数:**该方法接受**期望值**为期望值，**新值**为新设定值。

**返回值:**此方法成功返回**真**。

以下程序说明了 weakCompareAndSet()方法:
**程序 1:**

```java
// Java program to demonstrate
// AtomicReference.weakCompareAndSet() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        // which stores Integer.
        AtomicReference<Integer> ref
            = new AtomicReference<Integer>();

        // set some value
        ref.set(999);

        // apply weakCompareAndSet()
        boolean result
            = ref.weakCompareAndSet(999,
                                    999999);

        // print value
        System.out.println("Setting new value"
                           + " is successful = "
                           + result);
        System.out.println("New Value = "
                           + ref.get());
    }
}
```

**Output:**

```java
Setting new value is successful = false
New Value = 999

```

**程序 2:**

```java
// Java program to demonstrate
// AtomicReference.weakCompareAndSet() method

import java.util.concurrent.atomic.AtomicReference;

public class GFG {
    public static void main(String[] args)
    {

        // create an atomic reference object
        // which stores String.
        AtomicReference<String> ref
            = new AtomicReference<String>();

        // set some value
        ref.set("GEEKS FOR GEEKS");

        // apply weakCompareAndSet()
        ref.weakCompareAndSet("GEEKS FOR GEEKS",
                              "GFG");

        // print value
        System.out.println("Value  = "
                           + ref.get());
    }
}
```

**Output:**

```java
Value  = GFG

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic reference . html # weakCompareAndSet(V，V)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReference.html#weakCompareAndSet(V, V))