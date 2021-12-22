# Java 中的 HashSet remove()方法

> 原文:[https://www . geesforgeks . org/hashset-remove-method-in-Java/](https://www.geeksforgeeks.org/hashset-remove-method-in-java/)

HashSet remove()方法用于从 HashSet 中移除特定元素。请注意，它仅在 JDK 1.2 版之后和之前，并且会在 JDK 1 和 JDK1.1 版之前抛出编译错误

> **注意:**如果指定的元素存在于 HashSet 中，则该方法返回 true，否则返回 boolean false。

**语法:**

```
HashSet.remove(Object O)
```

**参数:**参数 *O* 属于哈希集类型，指定要从哈希集中移除的元素。

**返回值:**布尔真假

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate
// HashSet.remove() method
// over String Elements

// Importing required classes
import java.util.*;

// Main class
// HashSet demo
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating an empty HashSet
        // Declaring object of string type
        HashSet<String> set = new HashSet<String>();

        // Adding custom input elements into the Set
        // using add() method
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("For");
        set.add("Geeks");

        // Displaying the HashSet(object elements)
        System.out.println("HashSet: " + set);

        // Removing elements
        // using remove() method
        set.remove("Geeks");
        set.remove("For");
        set.remove("Welcome");

        // Now displaying the HashSet after removal
        // of elements from it
        System.out.println(
            "HashSet after removing elements: " + set);
    }
}
```

**Output**

```
HashSet: [Geeks, For, Welcome, To]
HashSet after removing elements: [To]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate remove()
// method of Hashset class
// over Integer Elements

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating an empty HashSet
        // Declaring object of integer type
        HashSet<Integer> set = new HashSet<Integer>();

        // Adding custom input elements into the Set
        // using add() method
        set.add(5);
        set.add(3);
        set.add(1);
        set.add(4);
        set.add(3);

        // Displaying the HashSet(object elements)
        System.out.println("HashSet: " + set);

        // Removing elements
        // using remove() method
        set.remove(3);
        set.remove(1);

        // Now displaying the HashSet after removal
        // of elements from it
        System.out.println(
            "HashSet after removing elements: " + set);
    }
}
```

**Output**

```
HashSet: [1, 3, 4, 5]
HashSet after removing elements: [4, 5]
```