# Java 中的 AtomicIntegerArray getAndUpdate()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicntegerarray-getandupdate-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-getandupdate-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicIntegerArray . Getandupdate()**是 Java 中的一个内置方法，它在对 atomicntegerarray 的任何给定索引处的值应用给定的更新函数后，更新该索引处的值。该方法将 AtomicIntegerArray 的索引值和更新函数作为参数，并通过对该值应用更新函数来更新该索引处的值。该函数应该没有副作用，因为当尝试的更新由于线程之间的争用而失败时，它可能会被重新应用。 **getAndUpdate()** 和 **updateAndGet()** 函数唯一的区别是前者返回更新前的值，后者返回更新后的值。

**语法:**

> 公共最终 int getAndUpdate(int i，intunaryooperator updateFunction)

 **参数:**该函数接受两个参数:

*   *i* 是要进行更新的索引。
*   *updateFunction* 是单个参数的更新函数，告知要进行什么更新。

**返回值:**该函数返回一个整数值，该整数值是应用指定更新函数后的值。

以下程序说明了上述方法:
**程序 1:**

```
// Java program that demonstrates
// the getAndUpdate() function

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
        IntUnaryOperator squaredFunction = (l) -> l * l;

        // Updating the value at idx
        // applying updateFunction and
        // storing the previous value
        int prev = arr.getAndUpdate(idx, squaredFunction);

        // Displaying the previous value
        System.out.println("The value before update"
                           + " at index " + idx
                           + " is " + prev);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```
The array : [1, 2, 3, 4, 5]
The value before update at index 3 is 4
The array after update : [1, 2, 3, 16, 5]

```

**程序 2:**

```
// Java program that demonstrates
// the getAndUpdate() function

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
        // applying updateFunction and
        // storing the previous value
        int prev = arr.getAndUpdate(idx, cubeFunction);

        // Displaying the previous value
        System.out.println("The value before update"
                           + " at index " + idx
                           + " is " + prev);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```
The array : [1, 2, 3, 4, 5]
The value before update at index 3 is 4
The array after update : [1, 2, 3, 64, 5]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicintegerarray . html # getAndUpdate-int-Java . util . function . intunaryooperator-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#getAndUpdate-int-java.util.function.IntUnaryOperator-)