# Java 番石榴| Longs.asList()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-as list-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-aslist-method-with-examples/)

番石榴的 [Longs 类](https://www.geeksforgeeks.org/longs-class-guava-java/)的 **Longs.asList()** 方法接受一个**长数组**作为参数，返回一个固定大小的列表。返回的列表由作为参数传递的长数组支持。这意味着在作为参数传递的数组中所做的更改将反映在方法返回的列表中，反之亦然。

**语法:**

> 公共静态列表< **长** > asList(长… backingArray)

**参数:**该方法接受一个强制参数 **backingArray** ，这是一个用于支持列表的长数组。

**返回值:**方法 *Longs.asList()* 返回一个固定大小的列表，该列表由作为参数传递给方法的数组支持。换句话说，该方法返回数组的列表视图。

下面的例子说明了上述方法的实现:

**例 1:**

```
// Java code to show implementation of
// Guava's Longs.asList() method

import com.google.common.primitives.Longs;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Long array
        long arr[] = { 1, 2, 3, 4, 5 };

        // Using Longs.asList() method to wrap
        // the specified primitive Long array
        // as a List of the Long type
        List<Long> myList = Longs.asList(arr);

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
// Guava's Longs.asList() method

import com.google.common.primitives.Longs;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Long array
        long arr[] = { 3, 5, 7 };

        // Using Longs.asList() method to wrap
        // the specified primitive Long array
        // as a List of the Long type
        List<Long> myList = Longs.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出:**

```
[3, 5, 7]

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/primitives/longs . html # asList-long……-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#asList-long...-)