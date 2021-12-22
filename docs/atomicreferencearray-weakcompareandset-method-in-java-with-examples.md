# Java 中的原子引用数组 weakCompareAndSet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicreferencearray-weakcompareandset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-weakcompareandset-method-in-java-with-examples/)

**原子引用数组**类的 **weakCompareAndSet()** 方法用于将索引 I 处的元素的值自动设置为新值，如果当前值等于作为参数传递的预期值，则设置为原子引用数组的新值。这个方法使用内存读取语义更新索引 I 处的值，就像变量被声明为可变类型的变量一样。如果向原子引用设置新值成功，则此方法返回 true。

**语法:**

```java
public final boolean
       weakCompareAndSet(
           int i, E expectedValue, E newValue)

```

**参数:**该方法接受:

*   **i** 是执行操作的原子引用数组的索引，
*   **期望值**是期望值，并且
*   **新值**是要设置的新值。

**返回值:**如果给 AtomicReference 设置新值成功，该方法返回 **true** 。

以下程序说明了 weakCompareAndSet()方法:
**程序 1:**

```java
// Java program to demonstrate
// weakCompareAndSet() method

import java.util.concurrent.atomic.*;

public class GFG {

    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReferenceArray<Integer> ref
            = new AtomicReferenceArray<Integer>(5);

        // set some value
        ref.set(0, 543);
        ref.set(1, 124);
        ref.set(2, 322);

        // apply weakCompareAndSet()
        boolean result
            = ref.weakCompareAndSet(0, 124,
                                    234);

        // print value
        System.out.println("Setting new value"
                           + " is successful = "
                           + result);

        System.out.println("Value of index 0 = "
                           + ref.get(0));
    }
}
```

**Output:**

```java
Setting new value is successful = false
Value of index 0 = 543

```

**程序 2:**

```java
// Java program to demonstrate
// weakCompareAndSet() method

import java.util.concurrent.atomic.*;

public class GFG {

    public static void main(String[] args)
    {

        // create an atomic reference object.c
        AtomicReferenceArray<String> ref
            = new AtomicReferenceArray<String>(5);

        // set some value
        ref.set(0, "INDIA");
        ref.set(1, "US");
        ref.set(2, "UK");
        ref.set(3, "CHINA");
        ref.set(4, "CHINA");

        // apply weakCompareAndSet()
        boolean result
            = ref.weakCompareAndSet(4, "CHINA",
                                    "CANADA");

        // print value
        System.out.println("Setting new value"
                           + " is successful = "
                           + result);

        System.out.println("Value of index 4 = "
                           + ref.get(4));
    }
}
```

**Output:**

```java
Setting new value is successful = true
Value of index 4 = CANADA

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic referencearray . html # weakCompareAndSet(V，V)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#weakCompareAndSet(V, V))