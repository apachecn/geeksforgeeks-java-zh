# 反向列表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到反向列表/](https://www.geeksforgeeks.org/java-program-to-reverse-a-list/)

反转列表意味着在反转列表之后，第一个元素应该与最后一个元素交换，第二个元素应该与第二个最后一个元素交换，以此类推，直到中间元素和结果列表是反转列表。

**示例:**

```
Input:
"PLATFORM", "LEARNING",  "BEST", "THE", "IS", "GFG"
Output:
Reverse order of given List :- 
[GFG, IS, THE, BEST, LEARNING, PLATFORM]
```

我们主要可以通过三种方式来反转列表:

1.  递归地
2.  使用集合。反向()
3.  使用 List.add()和 List.remove 方法

**方法一:使用** [**递归**](https://www.geeksforgeeks.org/recursion/)

函数直接或间接调用自身的过程称为递归，相应的函数称为递归函数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Reverse a List recursively

import java.io.*;
import java.util.*;

class GFG {
    public static <T> void revlist(List<T> list)
    {
        // base condition when the list size is 0
        if (list.size() <= 1 || list == null)
            return;

        T value = list.remove(0);

        // call the recursive function to reverse
        // the list after removing the first element
        revlist(list);

        // now after the rest of the list has been
        // reversed by the upper recursive call,
        // add the first value at the end
        list.add(value);
    }
    public static void main(String[] args)
    {
        System.out.println(
            "Reverse order of given List :- ");

        List<String> gfg = new ArrayList<>(
            Arrays.asList("PLATFORM", "LEARNING",  "BEST", "THE", "IS", "GFG"));

        revlist(gfg);

        System.out.println(gfg);
    }
}
```

**Output**

```
Reverse order of given List :- 
[GFG, IS, THE, BEST, LEARNING, PLATFORM]
```

**方法二:使用**[**collections . reverse()**](https://www.geeksforgeeks.org/collections-reverse-java-examples/)

java.util.Collections.reverse()方法是 java.util.Collections 类方法。它颠倒了作为参数传递的列表中元素的顺序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to reverse the list
// using Collections.reverse() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        List<Integer> number = new ArrayList<>(
            Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8));

        System.out.println(
            "Reverse order of given List :- ");

        // the number list will be reversed using this method
        Collections.reverse(number);

        System.out.println(number);
    }
}
```

**Output**

```
Reverse order of given List :- 
[8, 7, 6, 5, 4, 3, 2, 1]
```

**方法三:使用**[**list . add()**](https://www.geeksforgeeks.org/list-add-method-in-java-with-examples/)**+list . remove()**

List 接口的 List.add()方法用于将参数中指定的元素追加到列表的末尾。

List 接口的 List.remove()方法用于从列表中移除参数中的指定元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to reverse the list using List.add()
// and List.remove() method

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        List<Integer> number = new ArrayList<>(
            Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8));

        System.out.println(
            "Reverse order of given List :- ");

        for (int k = 0, j = number.size() - 1; k < j; k++)
        {
            number.add(k, number.remove(j));
        }

        System.out.println(number);
    }
}
```

**Output**

```
Reverse order of given List :- 
[8, 7, 6, 5, 4, 3, 2, 1]
```