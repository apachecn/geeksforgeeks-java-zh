# 爪哇番石榴| Lists.reverse()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-list-reverse-method-with-examples/](https://www.geeksforgeeks.org/java-guava-lists-reverse-method-with-examples/)

番石榴的**list . reverse()**方法接受一个列表作为参数，并返回作为参数传递的列表的反向视图。如果指定的列表是随机访问的，那么返回的列表也是随机访问的。

**例如:**list . reverse(arrays . aslist(1，2，3))返回一个包含 3，2，1 的列表。

**语法:**

```
public static <T> List<T> reverse(List<T> list)

```

**参数:**该方法接受**列表**作为参数，并返回一个由该列表支持的列表。这意味着在返回的列表中所做的更改会反映在作为参数传递给方法的列表中，反之亦然。

**返回值:**方法 Lists.reverse()返回作为参数传递的列表的反向视图。返回的列表支持作为参数传递的列表所支持的所有可选列表操作。

下面的例子说明了上述方法的实现:

**例 1:**

```
// Java code to show implementation of
// Guava's Lists.reverse() method

import com.google.common.collect.Lists;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a List of Integers
        List<Integer> myList
            = Arrays.asList(1, 2, 3, 4, 5);

        // Using Lists.reverse() method to get a
        // reversed view of the specified list. Any
        // changes in the returned list are reflected
        // in the original list and vice-versa
        List<Integer> reverse = Lists.reverse(myList);

        // Displaying the reversed view of specified List
        System.out.println(reverse);
    }
}
```

**输出:**

```
[5, 4, 3, 2, 1]

```

**例 2:**

```
// Java code to show implementation of
// Guava's Lists.reverse() method

import com.google.common.collect.Lists;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a List of Characters
        List<Character> myList
            = Arrays.asList('H', 'E', 'L', 'L', 'O');

        // Using Lists.reverse() method to get a
        // reversed view of the specified list. Any
        // changes in the returned list are reflected
        // in the original list and vice-versa
        List<Character> reverse = Lists.reverse(myList);

        // Displaying the reversed view of specified List
        System.out.println(reverse);
    }
}
```

**输出:**

```
[O, L, L, E, H]

```

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/collect/list . html # reverse-Java . util . list-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/collect/Lists.html#reverse-java.util.List-)