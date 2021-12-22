# 将地图内容复制到另一个哈希表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-copy-map-content-to-other-hashtable/](https://www.geeksforgeeks.org/java-program-to-copy-the-map-content-to-another-hashtable/)

[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)和[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)用于以键和值的形式存储数据，使用哈希技术来存储唯一的键。要将地图内容复制到 Java 中的另一个哈希表，可以使用 [putAll()](https://www.geeksforgeeks.org/hashmap-putall-method-in-java/) 方法。

**putAll()方法:**

方法将指定 hashmap 中的所有映射复制到 hashtable 中。这些映射替换该哈希表中当前在指定 hashmap 中的任何键的任何映射。

**语法:**

```java
hashtable.putAll(hashmap)
```

**参数:**该方法采用一个参数*散列表*，该散列表引用了我们想要复制的现有地图

**返回值:**该方法不返回值。

**异常:**如果我们要复制的地图为空，该方法将抛出*空指针异常*。

**将哈希表元素复制到哈希表的步骤**

1.  用一些元素创建一个新的散列表
2.  将映射放入 HashMap
3.  创建一个新的哈希表。
4.  使用 putAll()方法将元素从 HashMap 复制到 Hashtable

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to copy Map content to another Hashtable

import java.util.HashMap;
import java.util.Hashtable;
public class NewExample {
    public static void main(String a[])
    {
        // Create hashmap and insert elements
        HashMap<String, String> hashmap
            = new HashMap<String, String>();

          // Add mappings
        hashmap.put("key_1", "GeeksForGeeks");
        hashmap.put("key_2", "2020");

        // Create hashtable
        Hashtable<String, String> hashtable
            = new Hashtable<String, String>();

        // Use putAll to copy Map elements to hashtable.
        hashtable.putAll(hashmap);

        // Print hashtable elements
        System.out.println("Elements in hashtable: "
                           + hashtable);
    }
}
```

**Output**

```java
Elements in hashtable: {key_2=2020, key_1=GeeksForGeeks}
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to copy Map content to another Hashtable

import java.util.Hashtable;
import java.util.HashMap;

public class HashmapExample {
    public static void main(String[] args)
    {
        // Create HashMap and insert elements
        HashMap<String, String> hashmap
            = new HashMap<String, String>();

          // Add mappings
        hashmap.put("key_1", "GeeksForGeeks");
        hashmap.put("key_2", "2020");

        // Create Hashtable and insert elements
        Hashtable<String, String> hashtable
            = new Hashtable<String, String>();
        hashtable.put("key_1", "GFG");
        hashtable.put("key_3", "Java");
        hashtable.put("key_4", "Programming");

        System.out.println("Elements in HashMap : "
                           + hashmap);
        System.out.println(
            "Initial Elements in Hashtable : " + hashtable);

        // Use putAll() to copy Map elements to Hashtable
        // It replaces existing mapping of keys
        hashtable.putAll(hashmap);

        System.out.println(
            "After copying map elements in hashtable:");
        System.out.println("Elements in Hashtable : "
                           + hashtable);
    }
}
```

**Output**

```java
Elements in HashMap : {key_2=2020, key_1=GeeksForGeeks}
Initial Elements in Hashtable : {key_4=Programming, key_3=Java, key_1=GFG}
After copying map elements in hashtable:
Elements in Hashtable : {key_4=Programming, key_3=Java, key_2=2020, key_1=GeeksForGeeks}
```