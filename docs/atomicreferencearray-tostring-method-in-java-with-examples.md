# Java 中的 AtomicReferenceArray toString()方法，示例

> 原文:[https://www . geeksforgeeks . org/atomicreferencearray-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/atomicreferencearray-tostring-method-in-java-with-examples/)

**原子引用数组**类的 **toString()** 方法用于返回数组当前值的字符串表示。此方法用于将原子引用数组的内容表示为字符串

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回数组当前值的**字符串表示**。

下面的程序说明了 toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// toString() method

import java.util.concurrent.atomic.*;

public class GFG {

    public static void main(String[] args)
    {

        // create an atomic reference object.
        AtomicReferenceArray<Integer> ref
            = new AtomicReferenceArray<Integer>(5);

        // set some value
        ref.set(0, 234);
        ref.set(1, 134);
        ref.set(2, 325);

        // print the toString() return
        String toString = ref.toString();
        System.out.println(
            "String representation of"
            + " AtomicReferenceArray:\n"
            + toString);
    }
}
```

**Output:**

```java
String representation of AtomicReferenceArray:
[234, 134, 325, null, null]

```

**程序 2:**

```java
// Java program to demonstrate
// toString() method

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

        // print the toString() return
        String toString = ref.toString();
        System.out.println(
            "String representation of"
            + " AtomicReferenceArray:\n"
            + toString);
    }
}
```

**Output:**

```java
String representation of AtomicReferenceArray:
[AMAN, AMAR, SURAJ]

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/concurrent/atomic/atomic referencearray . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/util/concurrent/atomic/AtomicReferenceArray.html#toString)