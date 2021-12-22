# Java 中的 LinkedHashMap 和 linked hashset

> 原文:[https://www . geeksforgeeks . org/link edhashmap-and-link edhashset-in-Java/](https://www.geeksforgeeks.org/linkedhashmap-and-linkedhashset-in-java/)

[**链接的哈希表**](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 就像[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)一样，有一个额外的功能，即维护插入其中的元素的顺序。HashMap 提供了快速插入、搜索和删除的优势，但是它从来没有维护过 LinkedHashMap 提供的插入的轨迹和顺序，在那里元素可以按照它们的插入顺序被访问。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// working of LinkedHashMap
import java.util.*;

class LinkedHashMapExample {

    public static void main(String args[])
    {

        // create an instance of LinkedHashMap
        LinkedHashMap<Integer, String> lhm;
        lhm = new LinkedHashMap<Integer, String>();

        // insert element in LinkedHashMap
        lhm.put(100, "Amit");

        // insert first null key
        lhm.put(null, "Ajay");
        lhm.put(101, "Vijay");
        lhm.put(102, "Rahul");

        // insert second null key
        // which replace first null key value
        lhm.put(null, "Anuj");

        // insert duplicate
        // which replace first 102 key value
        lhm.put(102, "Saurav");

        // iterate and print the key/value pairs
        lhm.entrySet().stream().forEach((m) -> {
            System.out.println(m.getKey() + " "
                               + m.getValue());
        });
    }
}
```

**Output**

```java
100 Amit
null Anuj
101 Vijay
102 Saurav
```