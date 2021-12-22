# 使用 HashMap 查找字符串中单词出现的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-program-to-find-the-occurrence-in-string-use-hashmap/](https://www.geeksforgeeks.org/java-program-to-find-the-occurrence-of-words-in-a-string-using-hashmap/)

HashMap <key value="">提供 Java 的 Map 接口的基本实现，导入 [java.util.HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 包或其超类。哈希映射将数据存储在(键、值)对中，并由另一种类型的索引(例如整数)访问。一个对象被用作另一个对象的键。如果插入了重复的键，它将替换相应键的元素。</key>

**进场:**

*   在<string integer="">的 Java 中声明一个 HashMap</string>
*   拆分给定的字符串，并将单词存储到字符串数组中。
*   遍历数组，检查单词是否在 HashMap 中。
*   如果不在 HashMap 中，那么将单词存储为 key，将 1 存储为初始值；如果单词出现在 HashMap 中，则增加该单词的值。
*   遍历完成后，打印 HashMap。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find the occurrence
// of words in a String using HashMap.
import java.io.*;
import java.util.HashMap;
import java.util.Map;

class GFG {
    public static void main(String[] args)
    {

        // Declaring the String
        String str = "Alice is girl and Bob is boy";
        // Declaring a HashMap of <String, Integer>
        Map<String, Integer> hashMap = new HashMap<>();

        // Spliiting the words of string
        // and storing them in the array.
        String[] words = str.split(" ");

        for (String word : words) {

            // Asking whether the HashMap contains the
            // key or not. Will return null if not.
            Integer integer = hashMap.get(word);

            if (integer == null)
                // Storing the word as key and its
                // occurrence as value in the HashMap.
                hashMap.put(word, 1);

            else {
                // Incrementing the value if the word
                // is already present in the HashMap.
                hashMap.put(word, integer + 1);
            }
        }
        System.out.println(hashMap);
    }
}
```

**Output**

```
{Bob=1, Alice=1, and=1, is=2, girl=1, boy=1}
```

注意，在上面的代码中，我们使用了 Wrapper 类，即 Integer，因为 get(key)方法返回 null。

你也可以从上面的程序中取消整数变量的使用。

让我们看看下面的代码:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find the occurrence
// of words in a String using HashMap.
import java.io.*;
import java.util.HashMap;
import java.util.Map;

class GFG {
    public static void main(String[] args)
    {

        String str = "Alice is girl and Bob is boy";

        Map<String, Integer> hashMap = new HashMap<>();

        String[] words = str.split(" ");

        for (String word : words) {
            // containsKey(key) will return a boolean value
            // i.e. true if it contains the key and false if
            // it doesn't.
            if (hashMap.containsKey(word))
                hashMap.put(word, hashMap.get(word) + 1);

            else
                hashMap.put(word, 1);
        }

        System.out.println(hashMap);
    }
}
```

**Output**

```
{Bob=1, Alice=1, and=1, is=2, girl=1, boy=1}
```