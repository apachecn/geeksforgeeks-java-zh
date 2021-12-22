# AtomicIntegerArray get()方法在 Java 中用示例

> 原文:[https://www . geeksforgeeks . org/atomicintgerarray-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-get-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicIntegerArray . get()**是 Java 中的一个内置方法，可以在 atomicntegerarray 的任何位置获取当前值。此方法将索引值作为参数，并返回该索引处的值。

**语法:**

```java
public final int get(int i)

```

**参数:**该函数接受单个参数 *i* ，即要获取的索引值。

**返回值:**该函数返回索引 *i* 处的当前值。

下面的程序说明了上述方法:

**程序 1:**

```java
// Java program that demonstrates
// the get() function

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

        // Index to get
        int idx = 2;

        // Using get() to retrieve value at idx
        int val = arr.get(idx);

        // Displaying the value at idx
        System.out.println("Value at index " + idx
                           + " is " + val);
    }
}
```

**输出:**

```java
The array : [1, 2, 3, 4, 5]
Value at index 2 is 3

```

**程序二:**

```java
// Java program that demonstrates
// the get() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 12, 22, 23, 24, 25 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the AtomicIntegerArray
        System.out.println("The array : " + arr);

        // Index to get
        int idx = 4;

        // Using get() to retrieve value at idx
        int val = arr.get(idx);

        // Displaying the value at idx
        System.out.println("Value at index " + idx
                           + " is " + val);
    }
}
```

**输出:**

```java
The array : [12, 22, 23, 24, 25]
Value at index 4 is 25

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/atomicintgerarray . html # get(int)](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#get(int))