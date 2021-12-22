# 从 Java 中的 HashMap 获取键的集合视图

> 原文:[https://www . geeksforgeeks . org/get-set-view-key-from-hashmap-in-Java/](https://www.geeksforgeeks.org/getting-set-view-of-keys-from-hashmap-in-java/)

Java 的 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 类提供了哈希表数据结构的功能。这个类可以在 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中找到。实现[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)界面。它将元素存储在(键、值)对中，您可以通过另一种类型的索引(例如整数/字符串)来访问它们。这里，键被用作标识符，用于关联地图上的每个值。它可以存储不同的类型:整数键和字符串值，也可以存储相同的类型:整数键和整数值。

**示例:**

```
Given : HashMap = {[a, 1], [b, 3], [C, 1]}
**Output:** Keys = [a, b, c]

**Given :** HashMap<Key, Value> = {[2, "hello"], [1, "world"]} 
**Output:** Keys = [2, 1]
```

HashMap 类似于 HashTable，但是不同步。也允许存储空键，但是只能有一个空键，并且可以有任意数量的空值。

> HashMap <integer>GFG =新 HashMap<integer>()；</integer></integer> 
> 
> //以上是带有整数键和字符串值的 HashMap 对象的声明

java.util 包中的 Set 接口是一个无序的对象集合，其中不能存储重复的值

```
Set <Obj> set = new HashSet<Obj>( );
// Obj is the type of object to be stored in the Set
```

散列表中的键的集合视图以集合的形式返回散列表中所有键的集合。

**打印键:**

*   使用迭代器对象打印 while 循环中的所有键
*   直接传入 System.out.println()的打印集对象。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Getting Set view of keys from HashMap in Java
import java.io.*;
import java.util.*;
class GFG {
    public static void main(String[] args)
    {
        HashMap<Integer, String> GFG
            = new HashMap<Integer, String>();

        // Inserting 1 as key and Geeks as the value
        GFG.put(1, "Geeks");

        // Inserting 2 as key and For as the value
        GFG.put(2, "For");

        // Inserting 3 as key and Geeks as the value
        GFG.put(3, "Geeks");
        Set<Integer> Geeks = GFG.keySet();
        System.out.println("Set View of Keys in HashMap : "
                           + Geeks);
    }
}
```

**Output**

```
Set View of Keys in HashMap : [1, 2, 3]

```