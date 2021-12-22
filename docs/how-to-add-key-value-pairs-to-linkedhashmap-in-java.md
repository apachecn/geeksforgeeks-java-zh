# 如何在 Java 中给 LinkedHashMap 添加键值对？

> 原文:[https://www . geesforgeks . org/如何将键值对添加到 java 中的 linked hashmap/](https://www.geeksforgeeks.org/how-to-add-key-value-pairs-to-linkedhashmap-in-java/)

[**LinkedHashMap**](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 是一个哈希表和链表实现的 Map 接口。在 LinkedHashMap 中，键值对的顺序取决于键插入到映射中的顺序。插入顺序不影响键是否重新插入到映射中。

**例:**

```java
Input: 
     Key: 1
     Value : 1221
     Key: 2
     Value : 2112
Output:
    Keys : [1,2]
    Values : [1221,2112]
    Key-Value pairs : [1=1221, 2=2112]
```

**方法使用:**

1.  [Put (key, value)](https://www.geeksforgeeks.org/hashmap-put-method-in-java/) : The first parameter is the key and the second parameter is the value.
2.  [Key Set ()](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/) : Create a set of key elements included in the hash map.
3.  [Value ()](https://www.geeksforgeeks.org/hashmap-values-method-in-java/) : Create a set of hash table values.

**进场:**

1.  创建名为键和值的双变量
2.  接受用户在键和值中的输入
3.  使用 put()方法在链接哈希表中添加键值对

下面是上述方法的实现:

T3】JavaT5

```java
// Java Program to add key-value 
// pairs to LinkedHashMap
import java.util.*;
public class Main {

    public static void main(String[] args)
    {
        // create an instance of LinkedHashMap
        LinkedHashMap<Integer, Integer> map
            = new LinkedHashMap<Integer, Integer>();

        int num, key, val;
        num = 2;
        for (int i = 0; i < num; i++) {

            // Taking inputs from user
            key = i + 1;
            val = key * 10;

            // Add mappings using put method
            map.put(key, val);
        }
        // Displaying key
        System.out.println("Keys: " + map.keySet());

        // Displaying value
        System.out.println("Values: " + map.values());

        // Displaying key-value pair
        System.out.println("Key-Value pairs: "
                           + map.entrySet());
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(1)