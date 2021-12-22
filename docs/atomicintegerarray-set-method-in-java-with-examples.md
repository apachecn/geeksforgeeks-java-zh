# Java 中的 AtomicIntegerArray set()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicntegerarray-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-set-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicIntegerArray . set()**是 Java 中的一个内置方法，它在 atomicntegerarray 的任何位置设置一个给定值。此方法将 AtomicIntegerArray 的索引值作为参数，并更新该索引处的值。此方法不返回值。函数 **set()** 类似于 **getAndSet()** 函数，但是前者不返回任何值，而后者在给定索引处返回值，然后在该索引处设置新值。

**语法:**

```java
public final void set(int i, int newValue)
```

**参数:**该函数采用两个参数:

*   *I* –the index value to be updated.
*   *New value* –The new value to be updated at the index.

**返回值:**函数不返回值。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the set() function

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
        int idx = 0;

        // The new value to update at idx
        int val = 10;

        // Updating the value at
        // idx applying set
        arr.set(idx, val);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [10, 2, 3, 4, 5]

```

**程序二:**

```java
// Java program that demonstrates
// the set() function

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

        // The new value to update at idx
        int val = 100;

        // Updating the value at
        // idx applying set
        arr.set(idx, val);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**输出:**

```java
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 100, 5]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicintgerarray . html # set-int-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#set-int-int-)