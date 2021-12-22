# Java 中的 AtomicIntegerArray lazySet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicntegerarray-lazy set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-lazyset-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicIntegerArray . lazyset()**是 Java 中的一个内置方法，它最终会在 atomicntegerarray 的任何给定索引处设置一个给定值。该方法将 AtomicIntegerArray 的索引值和要设置的值作为参数，并在不返回任何内容的情况下更新以前的值。

**语法:**

```
public final void lazySet(int i, int newValue)
```

**参数:**函数取两个参数:

*   *I* , which is the index value to be updated.
*   *The new value* is the new value updated at the index.

**返回值:**函数不返回值。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program that demonstrates
// the lazySet() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicIntegerArray
        // with array a
        AtomicIntegerArray arr
            = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 0;

        // The new value to update at idx
        int val = 10;

        // Updating the value at
        // idx applying lazySet
        arr.lazySet(idx, val);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after"
                           + " update : "
                           + arr);
    }
}
```

**输出:**

```
The array : [1, 2, 3, 4, 5]
The array after update : [10, 2, 3, 4, 5]

```

**程序二:**

```
// Java program that demonstrates
// the lazySet() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicIntegerArray
        // with array a
        AtomicIntegerArray arr
            = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 3;

        // The new value to update at idx
        int val = 100;

        // Updating the value at
        // idx applying lazySet
        arr.lazySet(idx, val);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after "
                           + "update : "
                           + arr);
    }
}
```

**输出:**

```
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 100, 5]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicintgerarray . html # lazySet-int-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#lazySet-int-int-)