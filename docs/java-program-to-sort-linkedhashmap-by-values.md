# 通过值对链接的哈希表进行排序的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到排序-按值链接 hashmap/](https://www.geeksforgeeks.org/java-program-to-sort-linkedhashmap-by-values/)

LinkedHashMap 就像 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 一样，有一个额外的特性，即保持插入其中的元素的顺序。HashMap 提供了快速插入、搜索和删除的优势，但是它从来没有维护过 LinkedHashMap 提供的插入的轨迹和顺序，在那里元素可以按照它们的插入顺序被访问。

[因此 LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是 HashMap 的子类。现在，在[链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)中，必须保持插入顺序，因此将[链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)转换为列表，然后打印值按排序顺序排列的列表。

**图解:**

> ***输入:**LinkedHashMap = {“for”，2}、{“Geek”，3}、{“Geek”，1}}*
> 
> ***输出:***
> 
> *键- > Geeks:值->1*
> 
> T20】键- >为:值- >

**程序:**

1.  创建一个 LinkedHashMap 类的对象，其中该对象声明为整数和字符串类型。
2.  使用 put()方法将元素添加到在地图中创建的上述对象中。这里的元素是键值对。
3.  从地图中检索以上所有条目，并使用 *entrySet()* 方法将其转换为列表。
4.  使用自定义比较器对列表值进行排序。
5.  现在使用 Collections 类排序方法，在该方法中，我们使用自定义比较器来比较地图的值。
6.  打印以上列表对象，用于每个循环。

**实施:**

**示例**

## Java

```java
// java Program to Sort LinkedHashMap by Values

// Importing all classes
// from java.util package
import java.util.*;
import java.util.Collections;
import java.util.Comparator;
import java.util.LinkedHashMap;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of LinkedHashMap Class
        // Declaring object of Integer and String type
        LinkedHashMap<String, Integer> map
            = new LinkedHashMap<>();
        // Adding elements to the object of Map
        // using the put() method
        // Elements here are key-value pairs
        map.put("for", 2);
        map.put("Geek", 3);
        map.put("Geeks", 1);

        // Now, getting all entries from map and
        // convert it to a list using entrySet() method
        List<Map.Entry<String, Integer> > list
            = new ArrayList<Map.Entry<String, Integer> >(
                map.entrySet());

        // Using collections class sort method
        // and inside which we are using
        // custom comparator to compare value of map
        Collections.sort(
            list,
            new Comparator<Map.Entry<String, Integer> >() {
                // Comparing two entries by value
                public int compare(
                    Map.Entry<String, Integer> entry1,
                    Map.Entry<String, Integer> entry2)
                {

                    // Substracting the entries
                    return entry1.getValue()
                        - entry2.getValue();
                }
            });

        // Iterating over the sorted map
        // using the for each method
        for (Map.Entry<String, Integer> l : list) {

            // Printing the sorted map
            // using getKey()  and getValue() methods
            System.out.println("Key ->"
                               + " " + l.getKey()
                               + ": Value ->"
                               + l.getValue());
        }
    }
}
```

**输出**

```java
Key -> Geeks: Value ->1
Key -> for: Value ->2
Key -> Geek: Value ->3
```