# Java 中的 AtomicIntegerArray getAndIncrement()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicntegerarray-getandincrement-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-getandincrement-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicIntegerArray . GetAnDicrement()**是 Java 中的一个内置方法，它会自动将 atomicntegerarray 的任何索引处的值递增 1。该方法将 AtomicIntegerArray 的索引值作为参数，在递增之前返回该索引处的值，然后递增该索引处的值。函数 **getAndIncrement()** 类似于 **incrementAndGet()** 函数，但是前者返回增量之前的值，而后者返回增量操作之后的值。

 **语法:**

```java
public final int getAndIncrement(int i)
```

**参数:**该函数接受单个参数 *i* ，该参数是执行一次递增操作的索引。

**返回值:**该函数返回更新前该索引处的前一个值，该值在*整数*中。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the getAndIncrement() function

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
        // idx applying getAndIncrement
        // and storing the previous value
        int prev = arr.getAndIncrement(idx);

        // Previous value at idx before update
        System.out.println("Value at index " + idx
                           + " before the update is "
                           + prev);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [11, 12, 13, 14, 15]
Value at index 0 before the update is 11
The array after update : [12, 12, 13, 14, 15]

```

**程序 2:**

```java
// Java program that demonstrates
// the getAndIncrement() function

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
        int idx = 3;

        // Updating the value at
        // idx applying getAndIncrement
        // and storing the previous value
        int prev = arr.getAndIncrement(idx);

        // Previous value at idx before update
        System.out.println("Value at index " + idx
                           + " before the update is "
                           + prev);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [11, 12, 13, 14, 15]
Value at index 3 before the update is 14
The array after update : [11, 12, 13, 15, 15]

```

**注意:**函数 getAndIncrement()与 incrementAndGet()类似，但后者返回更新后的值，而前者返回更新后的前一个值。

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/atomicintgerarray . html # getandinecrement(int)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#getAndIncrement(int))