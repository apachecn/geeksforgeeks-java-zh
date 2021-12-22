# 如何在 Java 中将包含键和值的两个数组转换成 HashMap？

> 原文:[https://www . geesforgeks . org/如何将包含键和值的两个数组转换为 java 中的 hashmap/](https://www.geeksforgeeks.org/how-to-convert-two-arrays-containing-keys-and-values-to-hashmap-in-java/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 是 java 的[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)的一部分。它以键值对的形式存储数据。哈希表的这些值可以通过使用它们各自的键来访问，或者键值对可以使用它们的索引(整数类型)来访问。 **HashMap** 类似于 java 中的 [Hashtable](https://www.geeksforgeeks.org/hashtable-in-java/) 。Hashtable 和 HashMap 的主要区别在于 HashTable 是同步的，而 HashMap 不是。此外，一个哈希表可以有一个**空**键和任意数量的**空**值。哈希映射中没有保留插入顺序。在 HashMap 中，可以使用 **HashMap.put()** 方法添加键和值。我们还可以将两个包含键和值的数组转换成一个包含各自键和值的 HashMap。

**示例:**

```
keys = {1,2,3,4,5}
values = {"Welcome","To","Geeks","For","Geeks"}
HashMap = {1=Welcome, 2=To, 3=Geeks, 4=For, 5=Geeks}
```

**代码**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert two arrays containing keys and
// values into a HAshMap

import java.util.*;
import java.io.*;

class GFG {

    public static HashMap map(Integer[] keys,
                              String[] values)
    {
        // two variables to store the length of the two
        // given arrays
        int keysSize = keys.length;
        int valuesSize = values.length;

        // if the size of both arrays is not equal, throw an
        // IllegalArgumentsException
        if (keysSize != valuesSize) {
            throw new IllegalArgumentException(
                "The number of keys doesn't match the number of values.");
        }

        // if the length of the arrays is 0, then return an
        // empty HashMap
        if (keysSize == 0) {
            return new HashMap();
        }

        // create a new HashMap of the type of keys arrays
        // and values array
        HashMap<Integer, String> map
            = new HashMap<Integer, String>();

        // for every key, value
        for (int i = 0; i < keysSize; i++) {

            // add them into the HashMap by calling the
            // put() method on the key-value pair
            map.put(keys[i], values[i]);
        }

        // return the HashMap
        return map;
    }

    // Driver method
    public static void main(String[] args)
    {
        // create an array for keys
        Integer[] keys = { 1, 2, 3, 4, 5 };

        // create an array for value
        String[] values
            = { "Welcome", "To", "Geeks", "For", "Geeks" };

        // call the map() method over the keys[] array and
        // values[] array
        Map m = map(keys, values);

        // print the returned map
        System.out.println(m);
    }
}
```

**Output**

```
{1=Welcome, 2=To, 3=Geeks, 4=For, 5=Geeks}
```