# Java 中的 AtomicIntegerArray updateAndGet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicntegerarray-updateandget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-updateandget-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicIntegerArray . updateAnDget()**是 Java 中的一个内置方法，它在对 atomicntegerarray 的任何给定索引处的值应用给定的更新函数后，更新该索引处的值。该方法将 AtomicIntegerArray 的索引值和更新函数作为参数，并通过对该值应用更新函数来更新该索引处的值。该函数应该没有副作用，因为当尝试的更新由于线程之间的争用而失败时，它可能会被重新应用。

**语法:**

> 公共最终 int updateAndGet(int i，IntegerunAryooperator updateFunction)

**参数:**该函数接受两个参数:

*   *i* :这是要进行更新的索引。
*   *updateFunction* :这是单参数的更新函数，告诉要进行什么更新。

**返回值:**函数返回一个 int 值，该值是应用指定的更新函数后的值。

以下程序说明了上述方法:
**程序 1:**

```java
// Java program that demonstrates
// the updateAndGet() function

import java.util.concurrent.atomic.AtomicIntegerArray;
import java.util.function.IntUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where update is to be made
        int idx = 4;

        // Declaring the updateFunction
        IntUnaryOperator squaredFunction = (l) -> l * l;

        // Updating the value at idx
        // applying updateFunction
        arr.updateAndGet(idx, squaredFunction);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 4, 25]

```

**程序 2:**

```java
// Java program that demonstrates
// the updateAndGet() function

import java.util.concurrent.atomic.AtomicIntegerArray;
import java.util.function.IntUnaryOperator;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where update is to be made
        int idx = 3;

        // Declaring the updateFunction
        IntUnaryOperator cubeFunction = (l) -> l * l * l;

        // Updating the value at idx
        // applying updateFunction
        arr.updateAndGet(idx, cubeFunction);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 64, 5]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicintegerarray . html # updateAndGet-int-Java . util . function . intunaryooperator-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#updateAndGet-int-java.util.function.IntUnaryOperator-)