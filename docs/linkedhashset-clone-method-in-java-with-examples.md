# 用示例链接 Java 中的 HashSet 克隆()方法

> 原文:[https://www . geeksforgeeks . org/link edhashset-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedhashset-clone-method-in-java-with-examples/)

[LinkedHashSet 类](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/)的 clone()方法用于返回上述哈希集的浅拷贝。它只是创建了一个集合的副本。

```java
--> java.util Package
     --> LinkedHashSet Class
         --> ***clone()*** Method   
```

**语法:**

```java
linked_hash_set.clone()
```

**参数:**该方法不取任何参数。

**返回类型:**该方法只返回 LinkedHashSet 的一个副本。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to illustrate clone() Method
// of LinkedHashSet Class

// Importing required classes
import java.io.*;
import java.util.LinkedHashSet;

// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an empty LinkedHashSet
        LinkedHashSet<String> set
            = new LinkedHashSet<String>();

        // Adding elements into the Set
        // using add() method
        set.add("Welcome");
        set.add("To");
        set.add("Geeks");
        set.add("4");
        set.add("Geeks");

        // Displaying the LinkedHashSet
        System.out.println("LinkedHashSet: " + set);

        // Creating a new cloned Set
        LinkedHashSet cloned_set = new LinkedHashSet();

        // Cloning the above Set
        // using clone() method
        cloned_set = (LinkedHashSet)set.clone();

        // Displaying the new Set after Cloning
        System.out.println("The new set: " + cloned_set);
    }
}
```

**Output:** 

```java
LinkedHashSet: [Welcome, To, Geeks, 4]
The new set: [Welcome, To, Geeks, 4]
```