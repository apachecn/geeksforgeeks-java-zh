# Java 番石榴| Chars.asList()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-as list-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-aslist-method-with-examples/)

番石榴的 [Chars 类](https://www.geeksforgeeks.org/chars-class-guava-java/)的 **Chars.asList()** 方法接受一个 **char 数组**作为参数，并返回一个固定大小的列表。返回的列表由作为参数传递的 char 数组支持。这意味着在作为参数传递的数组中所做的更改将反映在方法返回的列表中，反之亦然。

**语法:**

> 公共静态列表< **字符** >列表(char… backingArray)

**参数:**该方法接受一个强制参数 **backingArray** ，这是一个用于支持列表的字符数组。

**返回值:**方法 *Chars.asList()* 返回一个固定大小的列表，该列表由作为参数传递给方法的数组支持。换句话说，该方法返回数组的列表视图。

下面的例子说明了上述方法的实现:

**例 1:**

```java
// Java code to show implementation of
// Guava's Chars.asList() method

import com.google.common.primitives.Chars;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Char array
        char arr[] = { 'a', 'b', 'c' };

        // Using Chars.asList() method to wrap
        // the specified primitive Char array
        // as a List of the Char type
        List<Character> myList = Chars.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出:**

```java
[a, b, c]

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Chars.asList() method

import com.google.common.primitives.Chars;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Char array
        char arr[] = { 'H', 'E', 'L', 'L', 'O' };

        // Using Chars.asList() method to wrap
        // the specified primitive Char array
        // as a List of the Char type
        List<Character> myList = Chars.asList(arr);

        // Displaying the elements in List
        System.out.println(myList);
    }
}
```

**输出:**

```java
[H, E, L, L, O]

```

**参考:**[https://Google . github . io/guava/releases/18.0/API/docs/com/Google/common/primitive/chars . html # asList(char…)](https://google.github.io/guava/releases/18.0/api/docs/com/google/common/primitives/Chars.html#asList(char...))