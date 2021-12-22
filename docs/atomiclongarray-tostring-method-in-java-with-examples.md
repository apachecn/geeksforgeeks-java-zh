# Java 中的 AtomicLongArray toString()方法，带示例

> 原文:[https://www . geeksforgeeks . org/atomicongarray-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomiclongarray-tostring-method-in-java-with-examples/)

**Java . util . concurrent . atomic . AtomicLongArray . tostring()**是 Java 中的一个内置方法，它返回一个字符串，该字符串文本表示 atomicongarray 的当前值。生成的字符串是一种简洁且信息丰富的表示，易于阅读。它用于轻松地将内容 AtomicLongArray 打印为字符串对象。

**语法:**

> 公共字符串 toString()

**参数:**函数不取参数。

**返回值:**函数返回 AtomicLongArray 当前值的字符串表示形式。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program that demonstrates
// the toString() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 1, 2, 3, 4, 5 };

        // Initializing an AtomicLongArray
        // with array a
        AtomicLongArray arr
            = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : "
                           + arr);

        // Displaying the string representation
        // of AtomicLongArray
        System.out.println("The string representation"
                           + " of the array: "
                           + arr.toString());
    }
}
```

**输出:**

```
The array : [1, 2, 3, 4, 5]
The string representation of the array: [1, 2, 3, 4, 5]

```

**程序二:**

```
// Java program that demonstrates
// the toString() function

import java.util.concurrent.atomic.AtomicLongArray;

public class GFG {
    public static void main(String args[])
    {
        // Initializing an array
        long a[] = { 11, 12, 13, 14, 15 };

        // Initializing an AtomicLongArray
        // with array a
        AtomicLongArray arr
            = new AtomicLongArray(a);

        // Displaying the AtomicLongArray
        System.out.println("The array : " + arr);

        // Displaying the string representation
        // of AtomicLongArray
        System.out.println("The string representation"
                           + " of the array: "
                           + arr.toString());
    }
}
```

**输出:**

```
The array : [11, 12, 13, 14, 15]
The string representation of the array: [11, 12, 13, 14, 15]

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/concurrent/atomicongarray . html # toString–](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/AtomicLongArray.html#toString--)