# 按字母顺序排列姓名的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-按字母顺序排序名称/](https://www.geeksforgeeks.org/java-program-to-sort-names-in-an-alphabetical-order/)

例如，按字母顺序对名称进行排序有多种方式对数组进行排序，如使用内置的 [Arrays.sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 方法或使用普通排序算法，如[冒泡排序](https://www.geeksforgeeks.org/java-program-for-bubble-sort/)、[合并排序](https://www.geeksforgeeks.org/merge-sort/)。这里我们使用冒泡排序和内置排序。

**例:**

```
Input : Array[] = {"Sourabh", "Anoop, "Harsh", "Alok", "Tanuj"}
Output: Array[] = {"Alok", "Anoop", "Harsh", "Sourabh", "Tanuj"}

Input : Array[] = {"Bob", "Alice"}
Output: Array[] = {"Alice", "Bob"}
```

**进场:蛮力进场**

其思想是在 unicode 的基础上比较字符串，并使用 [compareTo()](https://www.geeksforgeeks.org/compare-two-strings-lexicographically-in-java/?ref=rp) 方法根据两个字符串之间的比较结果根据返回的 int 值交换字符串。

在输入中，用户必须输入名称的数量和名称，在输出中，它将按字母顺序对它们进行排序和显示。为此，我们将使用 compareTo()方法，并将一个字符串与其余字符串进行比较。

**CompareTo()** 用于按字典顺序比较两个字符串。两个字符串的每个字符都被转换为其 **unicode** 值。词典顺序只不过是字母顺序。

此方法返回基于两个字符串之间比较的 int 数据类型。如果返回> 0，则传递给 compareTo()方法的参数首先是字典式的，而如果返回< 0，则调用该方法的字符串在字典式上是正确的。

**步骤**

*   Use the **comparison ()** method to compare one string with other strings.
*   Exchange elements based on the comparison between two strings.
*   Print the sorted names in alphabetical order.

下面是上述方法的实现:

T3】JavaT5

```
// Java Program to Sort Names in an Alphabetical Order
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // storing input in variable
        int n = 4;

        // create string array called names
        String names[]
            = { "Rahul", "Ajay", "Gourav", "Riya" };
        String temp;
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {

                // to compare one string with other strings
                if (names[i].compareTo(names[j]) > 0) {
                    // swapping
                    temp = names[i];
                    names[i] = names[j];
                    names[j] = temp;
                }
            }
        }

        // print output array
        System.out.println(
            "The names in alphabetical order are: ");
        for (int i = 0; i < n; i++) {
            System.out.println(names[i]);
        }
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(N <sup>2</sup> )

**方法:内置排序功能**

*   Use the built-in [arrays.sort ()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) method to sort the arrays.
*   Print the sorted names in alphabetical order.

下面是上述方法的实现:

T3】JavaT5

```
// Java Program to Sort Names in an Alphabetical Order
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // storing input in variable
        int n = 4;
        // create string array called names
        String names[]
            = { "Rahul", "Ajay", "Gourav", "Riya" };
        // inbuilt sort function
        Arrays.sort(names);
        // print output array
        System.out.println(
            "The names in alphabetical order are: ");
        for (int i = 0; i < n; i++) {
            System.out.println(names[i]);
        }
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(n log n)