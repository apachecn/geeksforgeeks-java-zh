# 如何在 Java 中将一个 HashMap 复制到另一个 HashMap？

> 原文:[https://www . geesforgeks . org/如何将一个 hashmap 复制到另一个 hashmap-in-java/](https://www.geeksforgeeks.org/how-to-copy-one-hashmap-to-another-hashmap-in-java/)

**HashMap** 与 [HashTable](https://www.geeksforgeeks.org/hashtable-in-java/) 相似，但不同步。它也允许存储空键，但是应该只有一个空键对象，并且可以有任意数量的空值。这个类不保证地图的顺序。要使用这个类及其方法，需要导入 **java.util.HashMap** 包或其超类。

给定一个 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) ，有三种方法可以将给定的 **HashMap** 复制到另一个:

1.  通常使用 put(k，v)方法迭代并将其放入另一个 HashMap。
2.  使用 putAll()方法。
3.  使用复制构造函数。

**方法 1:通过正常迭代并使用 put(k，v)方法将其放入另一个 HashMap。**

一个简单的解决方案是遍历地图，并对另一个地图中的每个映射键和值使用 [put(键，值)](https://www.geeksforgeeks.org/hashmap-put-method-in-java/#:~:text=put()%20method%20of%20HashMap,replaced%20by%20the%20new%20value.)一次。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to iterate through the
// first map and put it in the second map

import java.util.HashMap;
import java.util.Map;

class GFG {
    public static <K, V> Map<K, V>
    copyMap(Map<K, V> original)
    {

        Map<K, V> second_Map = new HashMap<>();

        // Start the iteration and copy the Key and Value
        // for each Map to the other Map.
        for (Map.Entry<K, V> entry : original.entrySet()) {

            // using put method to copy one Map to Other
            second_Map.put(entry.getKey(),
                           entry.getValue());
        }

        return second_Map;
    }

    public static void main(String[] args)
    {

        Map<String, Integer> hashMap = new HashMap<>();
        hashMap.put("A", 1);
        hashMap.put("B", 2);
        hashMap.put("C", 3);

        // copyMap method would copy the original
        // hashMap to second_Map
        Map<String, Integer> second_Map = copyMap(hashMap);

        System.out.println(second_Map);
    }
}
```

**Output**

```java
{A=1, B=2, C=3}
```

**方法二:采用普塔尔(k，v)法。**

[Map.putAll(k，v)](https://www.geeksforgeeks.org/hashmap-putall-method-in-java/#:~:text=putAll()%20is%20an%20inbuilt,from%20one%20map%20into%20another.&text=Parameters%3A%20The%20method%20takes%20one,we%20want%20to%20copy%20from.) 方法用于将一个 HashMap 复制到另一个空 HashMap。

**语法:**

```java
new_hash_map.putAll(*exist_hash_map*)
```

**参数:**方法取一个参数 *exist_hash_map* ，指的是我们要复制的现有地图。

**返回值:**该方法不返回值。

**异常:**如果我们要复制的地图为空，该方法抛出*空指针异常*。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to copy hashmap to
// another hashmap using putAll() method

import java.util.HashMap;
import java.util.Map;

class GFG {
    public static <K, V> Map<K, V>
    copyMap(Map<K, V> original)
    {

        Map<K, V> second_map = new HashMap<>();

        // using putAll method to copy from original Map to
        // second_map
        second_map.putAll(original);

        return second_map;
    }

    public static void main(String[] args)
    {

        Map<String, Integer> hashMap = new HashMap<>();

        hashMap.put("A", 1);
        hashMap.put("B", 2);
        hashMap.put("C", 3);

        // copyMap method would copy the original
        // hashMap to second_Map
        Map<String, Integer> second_map = copyMap(hashMap);

        System.out.println(second_map);
    }
}
```

**Output**

```java
{A=1, B=2, C=3}
```

**方法三:使用复制构造函数。**

将一个 HashMap 复制到另一个 HashMap 是最短和最简单的方法之一。

我们可以使用[复制构造器](https://www.geeksforgeeks.org/copy-constructor-in-java/)来复制一个地图，这是一个特殊的构造器，用于创建一个新的对象作为一个现有对象的副本。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.util.HashMap;
import java.util.Map;

class GFG {

    // using copy constructor to resturn the original map
    // and then copy it in second_map
    public static <K, V> Map<K, V> copyMap(Map<K, V> original)
    {
       // constructor by passing original hashmap
       // in the parameter returns the new hashmap
       // with the copied content of the original one
        return new HashMap<>(original);
    }

    public static void main(String[] args)
    {

        Map<String, Integer> hashMap = new HashMap<>();

        hashMap.put("A", 1);
        hashMap.put("B", 2);
        hashMap.put("C", 3);

        // copyMap method would copy the original
        // hashMap to second_Map
        Map<String, Integer> second_map = copyMap(hashMap);

        System.out.println(second_map);
    }
}
```

**Output**

```java
{A=1, B=2, C=3}
```