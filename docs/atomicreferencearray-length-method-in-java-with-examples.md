# Java 中的 AtomicReferenceArray length()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicreferencearray-length-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-length-method-in-java-with-examples/)

一个**原子引用数组**类的 **length()** 方法用来返回这个原子引用数组的长度。

**语法:**

```java
public final int length()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回表示该原子数组长度的**整数**。

下面的程序说明了 length()方法:
**程序 1:**

```java
// Java program to demonstrate
// AtomicReferenceArray.length() method

import java.util.concurrent.atomic.*;

public class GFG {

    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReferenceArray<Integer> ref
            = new AtomicReferenceArray<Integer>(5);

        // print the length
        int length = ref.length();
        System.out.println(
            "length of AtomicReferenceArray = "
            + length);
    }
}
```

**Output:**

```java
length of AtomicReferenceArray = 5

```

**程序 2:**

```java
// Java program to demonstrate
// AtomicReferenceArray.length() method

import java.util.concurrent.atomic.*;

public class GFG {

    public static void main(String[] args)
    {

        // create a array of Strings
        String[] names
            = { "AMAN", "AMAR", "SURAJ" };

        // create an atomic reference object.
        AtomicReferenceArray<String> ref
            = new AtomicReferenceArray<String>(names);

        // print the length
        int length = ref.length();
        System.out.println(
            "length of AtomicReferenceArray = "
            + length);
    }
}
```

**Output:**

```java
length of AtomicReferenceArray = 3

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic referencearray . html # length()](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#length)