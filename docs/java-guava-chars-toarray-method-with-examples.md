# Java 番石榴| Chars.toArray()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-to array-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-toarray-method-with-examples/)

番石榴库中 **[chars 类](https://www.geeksforgeeks.org/chars-class-guava-java/)** 的 **toArray()** 方法用于将作为参数传递给该方法的 Char 值转换为 Char 数组。这些字符值作为集合传递给此方法。此方法返回一个 Char 数组。

**语法:**

> 公共静态 char[] toArray(集合<character>集合)</character>

**参数:**该方法接受一个强制参数*集合*，该集合是要转换为字符数组的字符值的集合。

**返回值:**这个方法以相同的顺序返回一个包含与集合相同值的字符数组。

**异常:**如果传递的集合或其任何元素为空，该方法将抛出 ***空指针异常*** 。

下面的程序说明了 toArray()方法的使用:

**例 1 :**

```java
// Java code to show implementation of
// Guava's Chars.toArray() method

import com.google.common.primitives.Chars;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a List of Chars
        List<Character> myList
            = Arrays.asList('G', 'E', 'E', 'K', 'S');

        // Using Chars.toArray() method to convert
        // a List or Set of Char to an array of Char
        char[] arr = Chars.toArray(myList);

        // Displaying an array containing each
        // value of collection,
        // converted to a char value
        System.out.println(Arrays.toString(arr));
    }
}
```

**Output:**

```java
[G, E, E, K, S]

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Chars.toArray() method

import com.google.common.primitives.Chars;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {
            // Creating a List of Chars
            List<Character> myList
                = Arrays.asList('a', 'b', null);

            // Using Chars.toArray() method
            // to convert a List or Set of Char
            // to an array of Char.
            // This should raise "NullPointerException"
            // as the collection contains "null"
            // as an element
            char[] arr = Chars.toArray(myList);

            // Displaying an array containing each
            // value of collection,
            // converted to a char value
            System.out.println(Arrays
                                   .toString(arr));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.lang.NullPointerException

```

**参考:**
[https://Google . github . io/guava/releases/18.0/API/docs/com/Google/common/primitive/chars . html # to array(Java . util . collection)](https://google.github.io/guava/releases/18.0/api/docs/com/google/common/primitives/Chars.html#toArray(java.util.Collection))