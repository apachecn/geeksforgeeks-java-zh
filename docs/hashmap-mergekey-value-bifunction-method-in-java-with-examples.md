# Java 中的 HashMap 合并(键、值、双函数)方法，示例

> 原文:[https://www . geesforgeks . org/hashmap-merge key-value-bifunction-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashmap-mergekey-value-bifunction-method-in-java-with-examples/)

**[哈希映射类](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)** 的**合并(键、值、双功能)**方法用于使用给定的映射函数组合一个键的多个映射值。Bucket 实际上是数组的索引，这个数组在 HashMap 实现中叫做 table。因此，表[0]称为 bucket0，表[1]称为 bucket1，依此类推。

*   If the key does not exist or is associated with null, it only needs to output the key together with the corresponding value in Hashmap as a new entry.
*   However, if the key has saved some values, the remapping function will match the old and new values with the given key.
*   Merge. If the key is empty, it will always be mapped to bucket 0, because the null pointer **is abnormal**

而没有为空键计算哈希

**语法:**

```
public V merge(K key, V value,
    BiFunction remappingFunction)

```

**参数:**这个方法接受三个参数:

*   **key:** is the key that we have a specific value. If two keys have the same value, they will be merged.
*   **Value:** is the index corresponding to the specific key stored in the bucket.
*   **Double function:** is a function with two parameters, which is used to calculate a new mapping according to the old value and the given value.

**返回值:**如果键不存在或与 null 相关联，则该方法返回键及其值。ELse 如果键已经保存了任何值，它会使用映射技术将旧值与新值合并。

以下程序说明了合并(键、值、双功能)方法:

**程序 1:**

```
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap and add some values
        HashMap<Integer, String>
            map1 = new HashMap<>();
        map1.put(1, "L");
        map1.put(2, "M");
        map1.put(3, "N");

        HashMap<Integer, String>
            map2 = new HashMap<>();
        map2.put(1, "B");
        map2.put(2, "G");
        map2.put(3, "R");

        // print map details
        System.out.println("HashMap1: "
                           + map1.toString());

        System.out.println("HashMap2: "
                           + map2.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        map2.forEach(
            (key, value)
                -> map1.merge(
                    key,
                    value,
                    (v1, v2)
                        -> v1.equalsIgnoreCase(v2)
                               ? v1
                               : v1 + ", " + v2));

        // print new mapping
        System.out.println("New HashMap: " + map1);
    }
}
```

**输出:**

```
HashMap1: {1=L, 2=M, 3=N}
HashMap2: {1=B, 2=G, 3=R}
New HashMap: {1=L, B, 2=M, G, 3=N, R}

```

**程序二:**

```
// Java program to demonstrate
// computeIfAbsent(Key, Function) method.

import java.util.*;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        // create a HashMap and add some values
        HashMap<Integer, String>
            map1 = new HashMap<>();
        map1.put(1, "Ram");
        map1.put(2, "Rohan");
        map1.put(3, "Shivam");

        HashMap<Integer, String>
            map2 = new HashMap<>();
        map2.put(1, "Tushar");
        map2.put(10, "Satya");
        map2.put(12, "Sundar");

        // print map details
        System.out.println("HashMap1: "
                           + map1.toString());

        System.out.println("HashMap2: "
                           + map2.toString());

        // provide value for new key which is absent
        // using computeIfAbsent method
        map2.forEach(
            (key, value)
                -> map1.merge(
                    key,
                    value,
                    (v1, v2)
                        -> v1.equalsIgnoreCase(v2)
                               ? v1
                               : v1 + ", " + v2));

        // print new mapping
        System.out.println("New HashMap: " + map1);
    }
}
```

**输出:**

```
HashMap1: {1=Ram, 2=Rohan, 3=Shivam}
HashMap2: {1=Tushar, 10=Satya, 12=Sundar}
New HashMap: {1=Ram, Tushar, 2=Rohan, 3=Shivam, 10=Satya, 12=Sundar}

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/hashmap . html # merge-K-V-Java . util . function . bifunction-](https://docs.oracle.com/javase/8/docs/api/java/util/HashMap.html#merge-K-V-java.util.function.BiFunction-)