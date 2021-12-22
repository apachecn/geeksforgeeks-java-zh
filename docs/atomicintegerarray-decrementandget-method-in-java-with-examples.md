# Java 中的 AtomicIntegerArray 递减 Get()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicintgerarray-减量和 get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-decrementandget-method-in-java-with-examples/)

**Java . util . concurrent . atomic . atomicntegerarray . reductandGet()**是 Java 中的一个内置方法，它在给定的索引处自动将元素减 1。此方法将索引值和要添加的值作为参数，并返回此索引处的更新值。

**语法:**

```
public final int decrementAndGet(int i)
```

**参数:**该函数接受单个参数 *i* ，该参数是执行减 1 操作的索引。

**返回值:**该函数返回更新后的值，该值在*整数*中。

下面的程序说明了上述方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program that demonstrates
// the decrementAndGet() function

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
        // idx applying decrementAndGet
        arr.decrementAndGet(idx);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:** 

```
The array : [1, 2, 3, 4, 5]
The array after update : [1, 2, 3, 3, 5]
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program that demonstrates
// the decrementAndGet() function

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

        // Updating the value at
        // idx applying decrementAndGet
        arr.decrementAndGet(idx);

        // Displaying the AtomicIntegerArray
        System.out.println("The array after update : "
                           + arr);
    }
}
```

**Output:** 

```
The array : [1, 2, 3, 4, 5]
The array after update : [0, 2, 3, 4, 5]
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/atomic/atomicintegerarray . html #减量获取(int)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#decrementAndGet(int))