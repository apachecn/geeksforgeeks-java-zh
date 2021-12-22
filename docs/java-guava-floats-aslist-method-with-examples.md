# Java 番石榴| Floats.asList()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-as list-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-aslist-method-with-examples/)

番石榴的[浮动类](https://www.geeksforgeeks.org/floats-class-guava-java/)的 **Floats.asList()** 方法接受一个**浮动数组**作为参数，并返回一个具有固定大小的列表。返回的列表由作为参数传递的浮点数组支持。这意味着在作为参数传递的数组中所做的更改将反映在方法返回的列表中，反之亦然。

**语法:**

> 公共静态列表< **浮动** >列表(浮动… backingArray)

**参数:**该方法接受一个强制参数 **backingArray** ，这是一个用于支持列表的浮点数组。

**返回值:**方法 *Floats.asList()* 返回一个固定大小的列表，该列表由作为参数传递给方法的数组支持。换句话说，该方法返回数组的列表视图。

下面的例子说明了上述方法的实现:

**例 1:**

```
// Java code to show implementation of
// Guava's Floats.asList() method

import com.google.common.primitives.Floats;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Float array
        float arr[] = { 1.2f, 2.3f, 3.4f, 4.5f, 5.6f };

        // Using Floats.asList() method to wrap
        // the specified primitive Float array
        // as a List of the Float type
        List<Float> myList = Floats.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出:**

```
[1.2, 2.3, 3.4, 4.5, 5.6]

```

**例 2:**

```
// Java code to show implementation of
// Guava's Floats.asList() method

import com.google.common.primitives.Floats;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Float array
        float arr[] = { 3.2f, 5.5f, 7.6f };

        // Using Floats.asList() method to wrap
        // the specified primitive Float array
        // as a List of the Float type
        List<Float> myList = Floats.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出:**

```
[3.2, 5.5, 7.6]

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/floats . html # asList(float…)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#asList(float...))