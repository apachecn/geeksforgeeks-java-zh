# Java 番石榴| Bytes.asList()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-bytes-as list-method-with-examples/](https://www.geeksforgeeks.org/java-guava-bytes-aslist-method-with-examples/)

番石榴的[字节类](https://www.geeksforgeeks.org/bytes-class-guava-java/)的 **Bytes.asList()** 方法接受一个**字节数组**作为参数，并返回一个固定大小的列表。返回的列表由作为参数传递的字节数组支持。这意味着在作为参数传递的数组中所做的更改将反映在方法返回的列表中，反之亦然。

**语法:**

> 公共静态列表< **字节** > asList(字节… backingArray)

**参数:**该方法接受一个强制参数 **backingArray** ，它是一个字节数组，用于支持列表。

**返回值:**方法 *Bytes.asList()* 返回一个固定大小的列表，该列表由作为参数传递给方法的数组支持。换句话说，该方法返回数组的列表视图。

下面的例子说明了上述方法的实现:

**例 1:**

```
// Java code to show implementation of
// Guava's Bytes.asList() method

import com.google.common.primitives.Bytes;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Byte array
        byte arr[] = { 1, 2, 3, 4, 5 };

        // Using Bytes.asList() method to wrap
        // the specified primitive Byte array
        // as a List of the Byte type
        List<Byte> myList = Bytes.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出:**

```
[1, 2, 3, 4, 5]

```

**例 2:**

```
// Java code to show implementation of
// Guava's Bytes.asList() method

import com.google.common.primitives.Bytes;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Byte array
        byte arr[] = { 3, 5, 7 };

        // Using Bytes.asList() method to wrap
        // the specified primitive Byte array
        // as a List of the Byte type
        List<Byte> myList = Bytes.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出:**

```
[3, 5, 7]

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/bytes . html # asList(byte…)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Bytes.html#asList(byte...))