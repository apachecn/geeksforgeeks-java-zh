# 将 HashSet 转换为 Java 中的数组

> 原文:[https://www . geesforgeks . org/convert-hashset-to-array-in-Java/](https://www.geeksforgeeks.org/convert-hashset-to-array-in-java/)

Java [**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/) 类用于创建一个集合，该集合使用哈希表来存储元素。继承 [**抽象设置**](https://www.geeksforgeeks.org/abstractset-class-in-java-with-examples/) 类，实现**设置接口**。

HashSet 的要点是:

*   HashSet 仅包含**独特元素**。
*   HashSet 允许**为空**值。
*   在 HashSet 中插入元素是基于 hashcode 的。
*   HashSet 最适合用于搜索问题。

**将 HashSet 转换为数组有两种方式:**

1.  遍历 HashSet，并将每个元素添加到数组中。
2.  要将一个 HashSet 转换成 java 中的数组，我们可以使用 **toArray()** 的函数。

**方法 1:通过遍历集合将元素添加到数组中**

我们可以使用简单的 for 循环遍历集合，然后将元素逐个添加到数组中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert HashSet to array

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        HashSet<String> set = new HashSet<String>();
        set.add("1");
        set.add("13");
        set.add("27");
        set.add("87");
        set.add("19");

        System.out.println("Hash Set Contains :" + set);
        String arr[] = new String[set.size()];

        int i=0;

        // iterating over the hashset
        for(String ele:set){
          arr[i++] = ele;
        }

        for (String n : arr)
            System.out.println(n);
    }
}
```

**Output**

```
Hash Set Contains :[1, 13, 27, 19, 87]
1
13
27
19
87
```

**法二:用至** [**阵()**](https://www.geeksforgeeks.org/arraylist-toarray-method-in-java-with-examples/) **法**

**语法:**

```
public Object[] toArray()
           or
public <T> T[] toArray(T[] a)
```

**参数:**这个方法要么不接受参数，要么取一个数组**T【】a**作为参数，如果列表的元素足够大，这个数组就是要存储的数组；否则，将为此目的分配一个相同运行时类型的新数组。

**返回值:**该函数返回**一个包含该列表中所有元素的数组**。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert HashSet to array

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        HashSet<String> set = new HashSet<String>();
        set.add("1");
        set.add("13");
        set.add("27");
        set.add("87");
        set.add("19");

        System.out.println("Hash Set Contains :" + set);
        String arr[] = new String[set.size()];

        // toArray() method converts the set to array
        set.toArray(arr);

        for (String n : arr)
            System.out.println(n);
    }
}
```

**Output**

```
Hash Set Contains :[1, 13, 27, 19, 87]
1
13
27
19
87
```