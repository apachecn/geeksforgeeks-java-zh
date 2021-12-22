# Java 中的 atomic referencearray accumulate dget()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicreferencearray-accumulated get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-accumulateandget-method-in-java-with-examples/)

**AtomicReferenceArray** 类的**accumulated Agreet()**方法用于原子地更新 AtomicReferenceArray 索引 I 处的元素，将给定的累积函数应用于当前值和给定值，并返回更新后的值。累积函数应该没有副作用，因为当尝试的更新由于线程之间的争用而失败时，它可以被重新应用。该函数的第一个参数是索引 I 处的当前值，第二个参数是给定的更新。

**语法:**

```java
public final E accumulateAndGet(int i, E x,
     BinaryOperator<E> accumulatorFunction)

```

**参数:**该方法接受:

*   **i** 是要执行操作的原子引用数组的索引，接受
*   **x** 是更新后的值
*   **累积函数**是两个自变量的无副作用函数。

**返回值:**此方法返回**更新值**。

下面的程序说明了累计数()方法:
**程序 1:**

```java
// Java program to demonstrate
// accumulateAndGet() method

import java.util.concurrent.atomic.*;
import java.util.function.BinaryOperator;

public class GFG {
    public static void main(String args[])
    {
        // an array
        Integer a[] = { 123, 1232, 1433, 134, 13415, 1343 };

        // AtomicReferenceArray with array
        AtomicReferenceArray<Integer> array
            = new AtomicReferenceArray<>(a);

        // Print AtomicReferenceArray
        System.out.println(
            "The AtomicReferenceArray before update\n: "
            + array);

        // Index and Value to apply accumulateAndGet
        int index = 2;
        int E = 343;

        // Declaring the accumulatorFunction
        // applying function to add value as string
        BinaryOperator add
            = (u, v)
            -> u.toString()
                   + v.toString();

        // apply accumulateAndGet()
        array.accumulateAndGet(index, E, add);

        // print AtomicReferenceArray
        System.out.println(
            "The AtomicReferenceArray "
            + "after update \n: "
            + array);
    }
}
```

**Output:**![](img/5b76e61799fbec78e3b3149eed9a2cd6.png)

**程序 2:**

```java
// Java program to demonstrate
// accumulateAndGet() method

import java.util.concurrent.atomic.*;
import java.util.function.BinaryOperator;

public class GFG {
    public static void main(String args[])
    {
        // an array
        String a[] = { "GFG", "JS" };

        // AtomicReferenceArray with array
        AtomicReferenceArray<String> arra
            = new AtomicReferenceArray<>(a);

        // Print AtomicReferenceArray
        System.out.println(
            "The AtomicReferenceArray"
            + " before update \n: "
            + array);

        // Index and Value to apply accumulateAndGet
        int index = 1;
        String E = " PYTHON";

        // Declaring the accumulatorFunction
        // applying function to add value as string
        BinaryOperator add
            = (u, v)
            -> u.toString()
                   + " and "
                   + v.toString();

        // apply accumulateAndGet()
        array.accumulateAndGet(index, E, add);

        // print AtomicReferenceArray
        System.out.println(
            "The AtomicReferenceArray"
            + " after update \n: "
            + array);
    }
}
```

**Output:**![](img/4d5d2e9eecf2e3f8c71e3a54eaffe18b.png)

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic referencearray . html # accumulated gett(int，E，Java . util . function . binaryoperator)](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#accumulateAndGet(int, E, java.util.function.BinaryOperator))