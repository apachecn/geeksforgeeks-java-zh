# 将 HashSet 转换为 Java 中的数组列表

> 原文:[https://www . geesforgeks . org/convert-hashset-to-a-ArrayList-in-Java/](https://www.geeksforgeeks.org/convert-hashset-to-a-arraylist-in-java/)

[ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 类是一个可调整大小的数组，存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中。[数组](https://www.geeksforgeeks.org/arrays-in-java/)和 Java 中的 ArrayList 的区别在于，数组的大小不能修改(也就是说，如果您想在数组中添加/添加或删除元素，您必须创建一个新的数组。但是，可以在数组列表中添加/添加或删除元素，而不需要创建新的数组。

[Hashset](https://www.geeksforgeeks.org/hashset-in-java/) 类存在于 **java.util** 包中，用于创建使用哈希表存储数据项的集合。HashSet 通过使用散列机制来存储元素。HashSet 只包含唯一的元素，并且允许空值。HashSet 不维护插入顺序，元素是根据它们的 hashcode 插入的。HashSet 是搜索操作的最佳方法。

为了将 HashSet 转换为 ArrayList，我们需要使用 Arraylist 构造函数，并将 HashSet 实例作为构造函数参数传递。它会将 HashSet 中的所有元素复制到新创建的 ArrayList 中。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert HashSet to ArrayList
import java.io.*;
import java.util.ArrayList;
import java.util.HashSet;
class GFG {
    public static void main(String[] args)
    {

        HashSet<String> flower_set = new HashSet<>();

        flower_set.add("tulip");
        flower_set.add("rose");
        flower_set.add("orchid");
        flower_set.add("marie-gold");

        // Pass hashset to arraylist constructor
        ArrayList<String> flower_array
            = new ArrayList<>(flower_set);

        // all elements from hashset are copied to arraylist
        System.out.println(
            "Elements of flower Arraylist are :");
        System.out.println(flower_array);

        // using the get method of Arraylist to get the
        // element at index=0
        System.out.print("Element at index 0 is : "
                         + flower_array.get(0) + " ");
    }
}
```

**Output**

```
Elements of flower Arraylist are :
[marie-gold, rose, tulip, orchid]
Element at index 0 is : marie-gold
```

还有一种将 HashSet 对象转换成 ArrayList 的方法，就是使用 Java 8 中引入的 stream api。我们将使用 Collectors 类的 toList()方法将输入数据转换为列表，但是我们希望它是一个数组列表，所以我们将使用前面的这个(数组列表<类型对象>)将其类型转换为数组列表。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to convert the HashSet to ArrayList
// Using Stream Api Java 8

import java.io.*;
import java.util.*;
import java.util.stream.*;
class GFG {
    public static void main(String[] args)
    {
        HashSet<String> flower_set = new HashSet<>();

        flower_set.add("tulip");
        flower_set.add("rose");
        flower_set.add("orchid");
        flower_set.add("marie-gold");

        // Using stream api
        // and typecasting the List object to ArraylList
        ArrayList<String> flower_array
            = (ArrayList<String>)flower_set.stream()
                  .collect(Collectors.toList());

        // all elements from hashset are copied to arraylist
        System.out.println(
            "Elements of flower Arraylist are :");
        System.out.println(flower_array);

        // using the get method of Arraylist to get the
        // element at index=0
        System.out.print("Element at index 0 is : "
                         + flower_array.get(0) + " ");
    }
}
```

**Output**

```
Elements of flower Arraylist are :
[marie-gold, rose, tulip, orchid]
Element at index 0 is : marie-gold
```