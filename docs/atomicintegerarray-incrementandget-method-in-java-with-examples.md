# Java 中的 AtomicIntegerArray incrementAndGet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicintgerarray-incrementandget-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-incrementandget-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicIntegerArray . incrementandget()**是 Java 中的一个内置方法，它会自动将 atomicntegerarray 的任何索引处的值递增 1。该方法将 AtomicIntegerArray 的索引值作为参数，在该索引处递增该值，并返回递增后的值。函数**增量和获取()**类似于 **getAndIncrement()** 函数，但是前者返回增量后的值，而后者返回增量操作前的值。

**语法:**

```java
public final int incrementAndGet(int i)

```

**参数:**该函数接受单个参数 *i* ，该参数是执行一次递增操作的索引。

**返回值:**该函数返回增量运算后的值，该值在*整数*中。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the incrementAndGet() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 3;

        // Updating the value at
        // idx applying incrementAndGet
        arr.incrementAndGet(idx);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 5, 5]

```

**程序二:**

```java
// Java program that demonstrates
// the incrementAndGet() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 11, 12, 13, 14, 15 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 0;

        // Updating the value at
        // idx applying incrementAndGet
        arr.incrementAndGet(idx);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出:**

```java
The array : [11, 12, 13, 14, 15]
The array after update : [12, 12, 13, 14, 15]

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/atomicintgerarray . html # incrementAndGet(int)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#incrementAndGet(int))