# Java 中的 AtomicIntegerArray length()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicintgerarray-length-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicintegerarray-length-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicIntegerArray . length()**是 Java 中的一个内置方法，返回 atomicntegerarray 的长度。此方法不接受任何参数，并返回类型为 *int* 的原子数组的长度。

**语法:**

```
public final int length()

```

**参数:**函数不接受任何参数。

**返回值:**该函数返回原子数组的长度。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program that demonstrates
// the length() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 11, 12, 13, 14, 15 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the length of the AtomicIntegerArray
        System.out.println("The length of the array : "
                           + arr.length());
    }
}
```

**输出:**

```
The length of the array : 5

```

**程序二:**

```
// Java program that demonstrates
// the length() function

import java.util.concurrent.atomic.AtomicIntegerArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        int a[] = { 11, 12, 13, 14, 15, 16, 17 };

        // Initializing an AtomicIntegerArray with array a
        AtomicIntegerArray arr = new AtomicIntegerArray(a);

        // Displaying the length of the AtomicIntegerArray
        System.out.println("The length of the array : "
                           + arr.length());
    }
}
```

**输出:**

```
The length of the array : 7

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrent/atomicintgerarray . html # length()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/atomic/AtomicIntegerArray.html#length())