# Java 中的 AtomicLongArray get()方法，示例

> 原文:[https://www . geesforgeks . org/atomicongarray-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-get-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLongArray . get()**是 Java 中的一个内置方法，可以在 atomicongarray 的任何位置获取当前值。此方法将索引值作为参数，并返回该索引处的值。

**语法:**

```
public final long get(int i)

```

**参数:**该函数接受单个参数 *i* ，即要获取的索引值。

**返回值:**该函数返回索引 *i* 处的当前值。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program that demonstrates
// the get() function

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

        // Index to get
        int idx = 2;

        // Using get() to retrieve value at idx
        long val = arr.get(idx);

        // Displaying the value at idx
        System.out.println("Value at index " + idx
                           + " is " + val);
    }
}
```

**Output:**

```
The array : [1, 2, 3, 4, 5]
Value at index 2 is 3

```

**程序 2:**

```
// Java program that demonstrates
// the get() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 12, 22, 23, 24, 25 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Index to get
        int idx = 4;

        // Using get() to retrieve value at idx
        long val = arr.get(idx);

        // Displaying the value at idx
        System.out.println("Value at index " + idx
                           + " is " + val);
    }
}
```

**Output:**

```
The array : [12, 22, 23, 24, 25]
Value at index 4 is 25

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # get-int-](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#get-int-)