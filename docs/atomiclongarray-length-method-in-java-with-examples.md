# Java 中的 AtomicLongArray length()方法，带示例

> 原文:[https://www . geesforgeks . org/atomicongarray-length-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-length-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLongArray . length()**是 Java 中的一个内置方法，返回 atomicongarray 的长度。此方法不接受任何参数，并返回类型为 *int* 的 AtomicLongArray 的长度。

**语法:**

> 公共最终 int 长度()

**参数:**函数不接受任何参数。

**返回值:**函数返回 AtomicLongArray 的长度。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program that demonstrates
// the length() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 11, 12, 13, 14, 15 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the length of the AtomicLongArray
        System.out.println("The length of the array : "
                           + arr.length());
    }
}
```

**Output:**

```
The length of the array : 5

```

**程序 2:**

```
// Java program that demonstrates
// the length() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 11, 12, 13, 14, 15, 16, 17 };

        // Initializing an AtomicLongArray with array a
        AtomicLongArray arr = new AtomicLongArray(a);

        // Displaying the length of the AtomicLongArray
        System.out.println("The length of the array : "
                           + arr.length());
    }
}
```

**Output:**

```
The length of the array : 7

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomic/atomicongarray . html # length–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#length--)