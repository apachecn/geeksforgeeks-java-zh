# Java 中的 AtomicLongArray decrementAndGet()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-减量和 get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-decrementandget-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomicongarray . reductandGet()**是 Java 中的一个内置方法，它在给定的索引处自动将元素减 1。此方法将索引值和要添加的值作为参数，并返回此索引处的更新值。

**语法:**

```java
public final long decrementAndGet(int i)

```

**参数:**该函数接受单个参数 *i* ，该参数是执行减 1 操作的索引。

**返回值:**该函数返回更新后的值，该值在*长*内。

以下程序说明了上述方法:
**程序 1:**

```java
// Java program that demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 3;

        // Updating the value at
        // idx applying decrementAndGet
        arr.decrementAndGet(idx);

        // Displaying the AtomicLongArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 3, 5]

```

**程序 2:**

```java
// Java program that demonstrates
// the compareAndSet() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 0;

        // Updating the value at
        // idx applying decrementAndGet
        arr.decrementAndGet(idx);

        // Displaying the AtomicLongArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [0, 2, 3, 4, 5]

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html #减量 Get-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#decrementAndGet-int-)