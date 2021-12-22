# Java 中的 HashMap 克隆()方法

> 原文:[https://www.geeksforgeeks.org/hashmap-clone-method-in-java/](https://www.geeksforgeeks.org/hashmap-clone-method-in-java/)

让我们明确一下[的基础概念，java 中的浅拷贝和深拷贝](https://www.geeksforgeeks.org/difference-between-shallow-and-deep-copy-of-a-class/)。浅重复更快。然而，它处理指针和引用是“懒惰的”。它不是创建指针指向的特定知识的当代副本，而是简单地复制指针价格。因此，每一个第一个副本和副本都可以有引用常量底层知识的指针。另一方面，深度复制或深度重复真正克隆了底层数据。它不会在第一个副本和第二个副本之间共享。

java.util.HashMap.clone()方法存在于 java.util 包中，该包通常用于返回上述哈希映射的浅层副本。它只是创建了一个地图的副本。

![](img/ad065f73be9181e808039dc962a1e1bb.png)

**语法:**

```java
Hash_Map.clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法只返回 HashMap 的一个副本。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Illustrate the clone() Method by
// Mapping String Values to Integer Keys

// Importing utility classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty HashMap
        HashMap<Integer, String> hash_map
            = new HashMap<Integer, String>();

        // Mapping string values to int keys
        // Using put() method

        // Custom input values passed as arguments
        hash_map.put(10, "Geeks");
        hash_map.put(15, "4");
        hash_map.put(20, "Geeks");
        hash_map.put(25, "Welcomes");
        hash_map.put(30, "You");

        // Print and display the HashMap
        System.out.println("Initial Mappings are: "
                           + hash_map);

        // Print and display the cloned HashMap
        // using clone() method
        System.out.println("The cloned map look like this: "
                           + hash_map.clone());
    }
}
```

**Output:** 

```java
Initial Mappings are: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
The cloned map look like this: {25=Welcomes, 10=Geeks, 20=Geeks, 30=You, 15=4}
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate the clone() method by
// Mapping Integer Values to String Keys

// Importing utility classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty HashMap
        // Declaring objects of type integer and string
        HashMap<String, Integer> hash_map
            = new HashMap<String, Integer>();

        // Mapping int values to string keys
        // using put() method
        hash_map.put("Geeks", 10);
        hash_map.put("4", 15);
        hash_map.put("Geeks", 20);
        hash_map.put("Welcomes", 25);
        hash_map.put("You", 30);

        // Print and display the HashMap
        System.out.println("Initial Mappings are: "
                           + hash_map);

        // Print and display the cloned HashMap
        // using clone() method
        System.out.println("The cloned map look like this: "
                           + hash_map.clone());
    }
}
```

**Output:** 

```java
Initial Mappings are: {4=15, Geeks=20, You=30, Welcomes=25}
The cloned map look like this: {Geeks=20, 4=15, You=30, Welcomes=25}
```

> **注:**
> 
> *   相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。
> *   clone()方法进行浅层复制。但是这里原始的和克隆的 hashmap 中的值不会相互影响，因为使用了原始数据类型。