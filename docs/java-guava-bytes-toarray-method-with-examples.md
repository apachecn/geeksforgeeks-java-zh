# Java 番石榴| Bytes.toArray()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-bytes-to array-method-with-examples/](https://www.geeksforgeeks.org/java-guava-bytes-toarray-method-with-examples/)

番石榴库中 **[字节类](https://www.geeksforgeeks.org/bytes-class-guava-java/)** 的 **toArray()** 方法用于将作为参数传递给该方法的字节值转换为字节数组。这些字节值作为集合传递给此方法。此方法返回一个字节数组。

**语法:**

> 公共静态字节[] toArray(集合< **？扩展**号>集合)
> 
> 号

**参数:**该方法接受一个强制参数*集合*，它是要转换成字节数组的字节值的集合。

**返回值:**这个方法以相同的顺序返回一个包含与集合相同值的字节数组。

**异常:**如果传递的集合或其任何元素为空，该方法将抛出 ***空指针异常*** 。

下面的程序说明了 toArray()方法的使用:

**例 1:**

```java
// Java code to show implementation of
// Guava's Bytes.toArray() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a List of Bytes
        List<Byte> myList
            = Arrays.asList((byte)1,
                            (byte)2,
                            (byte)3,
                            (byte)4,
                            (byte)5);

        // Using Bytes.toArray() method to convert
        // a List or Set of Byte to an array
        // of Byte
        byte[] arr = Bytes.toArray(myList);

        // Displaying an array containing each
        // value of collection,
        // converted to a byte value
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出:**

```java
[1, 2, 3, 4, 5]

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Bytes.toArray() method

import com.google.common.primitives.Bytes;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {

            // Creating a List of Bytes
            List<Byte> myList
                = Arrays.asList((byte)2,
                                (byte)4,
                                null);

            // Using Bytes.toArray() method
            // to convert a List or Set of Byte
            // to an array of Byte.
            // This should raise "NullPointerException"
            // as the collection contains
            // "null" as an element
            byte[] arr = Bytes.toArray(myList);

            // Displaying an array containing each
            // value of collection,
            // converted to a byte value
            System.out.println(Arrays.toString(arr));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.NullPointerException

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/bytes . html # to array(Java . util . collection)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Bytes.html#toArray(java.util.Collection))