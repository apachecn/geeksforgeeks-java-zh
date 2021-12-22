# 如何在 Java 中将地图内容复制到另一个哈希表？

> 原文:[https://www . geeksforgeeks . org/如何将地图内容复制到另一个 java 哈希表/](https://www.geeksforgeeks.org/how-to-copy-map-content-to-another-hashtable-in-java/)

哈希表类实现了一个哈希表，它将键映射到值。任何非空对象都可以用作键或值。为了成功地从哈希表中存储和检索对象，用作键的对象必须实现 hashCode 方法和 equals 方法。

[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)和[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)用于以键和值的形式存储数据，使用哈希技术来存储唯一的键。要将地图内容复制到 Java 中的另一个哈希表，可以使用 [putAll()](https://www.geeksforgeeks.org/hashmap-putall-method-in-java/) 方法。

**putAll()方法:**该方法将指定散列表中的所有映射复制到散列表中。这些映射替换该哈希表中当前在指定 hashmap 中的任何键的任何映射。

**语法:**

```
hashtable.putAll(hashmap)
```

**参数:**方法取一个参数 *hashmap* ，指的是我们要复制的现有地图。

**返回值:**该方法不返回值。

**异常:**如果我们要复制的地图为空，该方法将抛出*空指针异常*。

**将哈希表元素复制到哈希表的步骤**

*   创建一个新的散列表并添加一些元素
*   将映射放入 HashMap
*   创建一个新的哈希表。
*   使用 **putAll()** 方法将元素从 HashMap 复制到 Hashtable

**示例:**

```
Input:

hs.put("first", "Geeks");
hs.put("second", "for");
hs.put("third", "Geeks");

Output:

{third=Geeks, second=for, first=Geeks}
{g2=g2 ans, g1=g1 ans, third=Geeks, second=for, first=Geeks}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to copy Map content to another Hashtable

import java.util.HashMap;
import java.util.Hashtable;
public class NewExample {
    public static void main(String a[])
    {
        // Create hashmap and insert elements
        HashMap<String, String> hashmap
            = new HashMap<String, String>();

        // Add mappings
        hashmap.put("k1", "GeeksForGeeks");
        hashmap.put("k2", "New Year");

        // Create hashtable
        Hashtable<String, String> hashtable
            = new Hashtable<String, String>();

        // Use putAll to copy Map elements to hashtable.
        hashtable.putAll(hashmap);

        // Print hashtable elements
        System.out.println("Hashtable elements: "
                           + hashtable);
    }
}
```

**Output**

```
Hashtable elements: {k2=New Year, k1=GeeksForGeeks}
```