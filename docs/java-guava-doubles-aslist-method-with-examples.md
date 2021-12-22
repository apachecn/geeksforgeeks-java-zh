# 爪哇番石榴| Doubles.asList()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-as list-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-aslist-method-with-examples/)

番石榴[双打类](https://www.geeksforgeeks.org/doubles-class-guava-java/)的**双打. asList()** 方法接受一个**双数组**作为参数，并返回一个具有固定大小的列表。返回的列表由作为参数传递的双数组支持。这意味着在作为参数传递的数组中所做的更改将反映在方法返回的列表中，反之亦然。

**语法:**

> 公共静态列表< **双** >列表(双… backingArray)

**参数:**该方法接受一个强制参数 **backingArray** ，这是一个双数组，用于支持列表。

**返回值:**方法 *Doubles.asList()* 返回一个固定大小的列表，该列表由作为参数传递给方法的数组支持。换句话说，该方法返回数组的列表视图。

下面的例子说明了上述方法的实现:

**例 1:**

```
// Java code to show implementation of
// Guava's Doubles.asList() method

import com.google.common.primitives.Doubles;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Double array
        double arr[] = { 1.2, 2.3, 3.4, 4.5, 5.6 };

        // Using Doubles.asList() method to wrap
        // the specified primitive Double array
        // as a List of the Double type
        List<Double> myList = Doubles.asList(arr);

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
// Guava's Doubles.asList() method

import com.google.common.primitives.Doubles;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Double array
        double arr[] = { 3.2, 5.5, 7.6 };

        // Using Doubles.asList() method to wrap
        // the specified primitive Double array
        // as a List of the Double type
        List<Double> myList = Doubles.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出:**

```
[3.2, 5.5, 7.6]

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitives/double . html # asList(double…)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#asList(double...))