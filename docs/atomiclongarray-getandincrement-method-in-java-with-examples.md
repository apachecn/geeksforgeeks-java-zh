# Java 中的 AtomicLongArray getAndIncrement()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-getandincrement-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-getandincrement-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLongArray . GetAnDicrement()**是 Java 中的一个内置方法，它会自动将 atomicongarray 的任何索引处的值递增 1。该方法将 AtomicLongArray 的索引值作为参数，在递增之前返回该索引处的值，然后递增该索引处的值。函数 **getAndIncrement()** 类似于 **incrementAndGet()** 函数，但是前者返回增量之前的值，而后者返回增量操作之后的值。
 **语法:**

> 公共最终长 getAndIncrement(int i)

**参数:**该函数接受单个参数 *i* ，该参数是执行一次递增操作的索引。

**返回值:**该函数返回更新前该索引处的前一个值，该值在*长*中。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the getAndIncrement() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 11, 12, 13, 14, 15 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 0;

        // Updating the value at
        // idx applying getAndIncrement
        // and storing the previous value
        long prev = arr.getAndIncrement(idx);

        // Previous value at idx before update
        System.out.println("Value at index " + idx
                           + " before the update is "
                           + prev);

        // Displaying the AtomicLongArray
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

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 11, 12, 13, 14, 15 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index where operation is performed
        int idx = 3;

        // Updating the value at
        // idx applying getAndIncrement
        // and storing the previous value
        long prev = arr.getAndIncrement(idx);

        // Previous value at idx before update
        System.out.println("Value at index " + idx
                           + " before the update is "
                           + prev);

        // Displaying the AtomicLongArray
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

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # getAndIncrement-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#getAndIncrement-int-)