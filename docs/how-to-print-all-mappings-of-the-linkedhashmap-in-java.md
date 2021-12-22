# 如何在 Java 中打印 LinkedHashMap 的所有映射？

> 原文:[https://www . geeksforgeeks . org/如何打印 java 中链接的所有映射/](https://www.geeksforgeeks.org/how-to-print-all-mappings-of-the-linkedhashmap-in-java/)

[链接散列表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)就像[散列表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)一样，有一个额外的特性，保持插入其中的元素的顺序。Java 中的 LinkedHashMap 是一个结合了 HashTable 和 LinkedList 实现的实现。它实现了映射接口。LinkedHashMap 的键值对具有可预测的迭代顺序。

我们可以使用 **entrySet()** 方法打印 LinkedHashMap 的所有映射，它返回 LinkedHashMap 对象中包含的所有条目。

**例:**

```
Input:
Key = ["1st-year", "2nd-year", "4th-year"]
Value = ["geeksforgeeks DSA course", "DBMS course", 
"Interview prep"]

Output:
1st-year : geeksforgeeks DSA course
2nd-year : DBMS course
4th-year : Interview prep

Input:
Key = [3, 2, 1]
Value = ["geeks", "for", "geeks"]

Output:
3 : geeks
2 : for
1 : geeks
```

**LinkedHashMap():** 这是用来构造默认的 LinkedHashMap 构造函数。

```
LinkedHashMap<K, V> l_map = new LinkedHashMap<K, V>();
Here, K is the key Object type and V is the value Object type.
```

**方法语法:**

```
l_map.entrySet()
```

**返回:**该方法以有序方式返回键值对。

**示例 1:** 以下实现使用键值对中的 entrySet()方法演示了 LinkedHashMap 的所有映射。

## Java

```
// Java program to Print all 
// Mappings of the LinkedHashMap
import java.util.*;

class IteratingOverLinkedHashMap {
    public static void main(String args[])
    {

        // create an instance of LinkedHashMap
        LinkedHashMap<String, String> l_map
            = new LinkedHashMap<String, String>();

        // Add mappings using put method
        l_map.put("1st-year", "geeksforgeeks DSA course");
        l_map.put("2nd-year", "DBMS course");
        l_map.put("4th-year", "Interview prep");

        // retrieve the key-value pairs as set using
        // entrySet & print each entry
        for (Map.Entry<String, String> mapElement :
             l_map.entrySet()) {

            // Finding the key
            String key = mapElement.getKey();

            // Finding the value
            String value = mapElement.getValue();

            // print the key : value pair
            System.out.println(key + " : " + value);
        }
    }
}
```

**输出**

```
1st-year : geeksforgeeks DSA course
2nd-year : DBMS course
4th-year : Interview prep
```

**示例 2:** 打印键值对的另一种方法是 LinkedHashMap 类的 **toString()** 方法。

## Java

```
// Java program to Print all 
// Mappings of the LinkedHashMap
import java.util.*;

class IteratingOverLinkedHashMap {
    public static void main(String args[])
    {

        // create an instance of LinkedHashMap
        LinkedHashMap<Integer, String> l_map
            = new LinkedHashMap<Integer, String>();
        LinkedHashMap<Integer, Integer> r_map
            = new LinkedHashMap<Integer, Integer>();

        // Add mappings using put method
        l_map.put(3, "geeks");
        l_map.put(2, "for");
        l_map.put(1, "geeks");

        // Add mappings using put method
        r_map.put(3, 1);
        r_map.put(2, 2);
        r_map.put(1, 3);

        // The toString method returns all mappings of
        // map where keys and values are separated by a =,
        // each mapping is separated by a comma and all
        // mappings are enclosed in { and }.
        System.out.println(r_map);

        // retrieve the key-value pairs as set using
        // entrySet & print each mapElement
        for (Map.Entry<Integer, String> mapElement :
             l_map.entrySet()) {

            // Finding the key
            Integer key = mapElement.getKey();

            // Finding the value
            String value = mapElement.getValue();

            // print the key : value pair
            System.out.println(key + " : " + value);
        }
    }
}
```

**输出**

```
{3=1, 2=2, 1=3}
3 : geeks
2 : for
1 : geeks
```

**时间复杂度:** O(n)，其中 n 为映射数。