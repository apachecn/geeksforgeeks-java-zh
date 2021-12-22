# 将数组列表转换为 Java 中的 linked hashmap

> 原文:[https://www . geesforgeks . org/convert-ArrayList-to-linked hashmap-in-Java/](https://www.geeksforgeeks.org/convert-arraylist-to-linkedhashmap-in-java/)

[LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 Java 中的一个预定义类，类似于 HashMap，包含 key 及其各自的值不像 HashMap，在 LinkedHashMap 中插入顺序是保留的。

我们需要把 ArrayList 转换成 LinkedHashMap linked hashmap 的 Key 值会是 ArrayList 的一个索引，基本上 linked hashmap 在迭代和存储数据方面也会和 ArrayList 一样。

**示例:**

```java
Input ArrayList :  { 5, 6, 7, 8, 4 } 

Output LinkedHashMap :

Index  |  Value
  1    |    5
  2    |    6
  3    |    7
  4    |    8
  5    |    4
```

**我们可以通过 2 种方式将 ArrayList 转换为 linked hashmap:**

1.  使用 for-each 循环遍历整个数组列表，并将每个元素推送到 LinkedHashMap。
2.  在 java 8 版本中使用[流](https://www.geeksforgeeks.org/stream-in-java/)。

**方法:使用每个循环**

*   在数组列表中获取输入。
*   使用 For/While 循环在 LinkedHashMap 中推送值(LinkedHashMap 的键将是数组列表的索引，假设第一个索引是 1)

**伪代码:**

```java
while (i < l1.size()) {

            l.put(i + 1, l1.get(i));
            i++; 
}

Here, "l1" is ArrayList and "l" is LinkedHashMap.
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert ArrayList
// to LinkedHashMap

import java.util.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        LinkedHashMap<Integer, Integer> l = new LinkedHashMap<>();

        ArrayList<Integer> l1 = new ArrayList<>();
        l1.add(5);
        l1.add(6);
        l1.add(7);
        l1.add(8);
        l1.add(4);

        int i = 0;

        // Adding one by one the elements 
        // of ArrayList to LinkedHashMap
        while (i < l1.size()) 
        {

            l.put(i + 1, l1.get(i));
            i++;
        }

        System.out.println("Key  |  Value");

        // .entrySet() method gives us the list of all 
        // mappings reference of the map
        for (Map.Entry<Integer, Integer> it :l.entrySet()) {

            System.out.println(" " + it.getKey() + "   |  "
                               + it.getValue());

        }
    }
}
```

**Output**

```java
Key  |  Value
 1   |  5
 2   |  6
 3   |  7
 4   |  8
 5   |  4
```

**时间复杂度:** O(n)

**方法 2:使用** [**溪流**](https://www.geeksforgeeks.org/stream-in-java/)

如果您使用的是 Java 8 或更高版本，还有另一种方法，可以使用**流**将 List 转换为 LinkedHashMap 对象。流应用编程接口用于处理对象集合。流是支持各种方法的对象序列，可以被流水线化以产生期望的结果。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert ArrayList to LinkedHashMap

import java.util.*;
import java.io.*;
import java.util.stream.Collectors;
class integer {

    private Integer id;
    private String name;

    public integer(Integer id, String name)
    {
        this.id = id;
        this.name = name;
    }

    public Integer getId() { return this.id; }

    // the .toString method of Object class
    // will be called by default when the object
    // of integer class will be made
    public String toString()
    {
        return "[" + this.id + "=>" + this.name + "]";
    }
}

class GFG {
    public static void main(String[] args)
    {

        List<integer> List = new ArrayList<integer>();

        List.add(new integer(1, "will"));
        List.add(new integer(2, "mike"));       
        List.add(new integer(3, "luke"));
        List.add(new integer(4, "dustin"));

        System.out.println("ArrayList contains: " + List);

        // stream Api is used here to convert the 
        // List to LinkedHashMap
        Map<Integer, integer> HashMap = List.stream().collect(Collectors.toMap(
                       integer::getId, integer -> integer));

        System.out.println("Map contains: " + HashMap); 
    }
}
```

**Output**

```java
ArrayList contains: [[1=>will], [2=>mike], [3=>luke], [4=>dustin]]
Map contains: {1=[1=>will], 2=[2=>mike], 3=[3=>luke], 4=[4=>dustin]}
```