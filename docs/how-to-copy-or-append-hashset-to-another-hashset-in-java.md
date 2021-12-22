# 如何在 Java 中将 HashSet 复制或追加到另一个 HashSet？

> 原文:[https://www . geesforgeks . org/how-copy-or-append-hashset-to-other-hashset-in-Java/](https://www.geeksforgeeks.org/how-to-copy-or-append-hashset-to-another-hashset-in-java/)

[**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/) 用于在 Java 中存储不同的值。HashSet 以随机顺序存储元素，因此无法保证元素的顺序。**HashSet**类实现了 [Set 接口](https://www.geeksforgeeks.org/set-in-java/) ，其背后是一个哈希表，该哈希表实际上是一个 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 实例。

我们可以将一个哈希集复制或附加到另一个哈希集。在 Java 中，有两种方法可以复制哈希集或将哈希集追加到另一个哈希集中:

*   使用 HashSet 构造函数
*   使用[克隆()](https://www.geeksforgeeks.org/clone-method-in-java-2/)方法
*   使用 addAll()方法

**方法 1:使用 HashSet 构造函数**

使用构造函数，我们可以绕过原始 HashSet 到构造函数，将原始 HashSet 复制到另一个 HashSet。

```java
// passing the original HashSet to the constructor

HashSet<Integer> copySet = new HashSet<>(originalSet)
```

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to copy a HashSet to
// another HashSet using the constructor

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New HashSet
        HashSet<Integer> set = new HashSet<>();

        // Add elements to original set
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(10);
        set.add(50);
        set.add(20);

        // Make a new HashSet and copy all elements of
        // original HashSet using constructor
        HashSet<Integer> copyOfSet = new HashSet<>(set);

        // Print original HashSet
        System.out.println("Original HashSet: " + set);

        // Print Copy HashSet
        System.out.println("Copy HashSet: " + copyOfSet);
    }
}
```

**Output**

```java
Original HashSet: [50, 20, 10, 30]
Copy HashSet: [50, 20, 10, 30]
```

**方法 2:使用克隆方法**

使用克隆方法，我们可以将原始 HashSet 的所有元素复制到 Java 中的另一个 HashSet。

**注:**元素的顺序可以相同，也可以不相同。所以不能保证订单。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to copy a HashSet to 
// another HashSet using clone method in Java

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New empty HashSet
        HashSet<Integer> set = new HashSet<>();

        // Add elements to set
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(10);
        set.add(50);
        set.add(20);

        // Create a new HashSet to copy the original HashSet
        HashSet copyOfSet = new HashSet();

        // Copy HashSet using clone method
        copyOfSet = (HashSet)set.clone();

        // Print original HashSet
        System.out.println("Original HashSet: " + set);

        // Print Copy HashSet
        System.out.println("Copy HashSet: " + copyOfSet);
    }
}
```

**Output**

```java
Original HashSet: [50, 20, 10, 30]
Copy HashSet: [50, 10, 20, 30]
```

**方法 3:使用 addAll 方法**

我们可以使用 [addAll()](https://www.geeksforgeeks.org/java-util-arraylist-addall-method-java/) 方法将一个哈希集复制或附加到另一个哈希集。Java 中的 addAll 方法将所有元素添加到 HashSet 中。

**注:**元素的顺序可以相同，也可以不相同。所以不能保证订单。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to copy a HashSet to 
// another HashSet using addAll method in Java 

import java.util.*;

public class GFG {
  public static void main(String[] args) {

    // New empty HashSet
    HashSet<Integer> set = new HashSet<>();

    // Add elements to set
    set.add(10);
    set.add(20);
    set.add(30);
    set.add(10);
    set.add(50);
    set.add(20);

    // Create a new HashSet to copy the original HashSet
    HashSet<Integer> copyOfSet = new HashSet<>();

    // Copy HashSet using addAll method
    copyOfSet.addAll(set);

    // Print original HashSet 
    System.out.println("Original HashSet: " + set);

    // Print Copy HashSet
    System.out.println("Copy HashSet: " + copyOfSet);

  }
}
```

**Output**

```java
Original HashSet: [50, 20, 10, 30]
Copy HashSet: [50, 20, 10, 30]
```

**在已经存在的 HashSet 中使用 addAll 方法追加:**

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to copy a HashSet to another 
// HashSet using addAll method in Java

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // New empty HashSet
        HashSet<Integer> set = new HashSet<>();

        // Add elements to set
        set.add(10);
        set.add(20);
        set.add(30);
        set.add(10);
        set.add(50);
        set.add(20);

        // Create a new HashSet to append a HashSet
        HashSet<Integer> appendedSet = new HashSet<>();

        // Add elements to appendedSet
        appendedSet.add(100);
        appendedSet.add(200);

        System.out.println("Before appending :");

        // Print original HashSet
        System.out.println("Original HashSet: " + set);

        // Print appendedSet before append
        System.out.println("Appended HashSet: "
                           + appendedSet);

        // Add all elements of set HashSet to appendedSet
        // using addAll method
        appendedSet.addAll(set);

        System.out.println("After appending");

        // Print appendedSet after append
        System.out.println("Appended HashSet: "
                           + appendedSet);
    }
}
```

**Output**

```java
Before appending :
Original HashSet: [50, 20, 10, 30]
Appended HashSet: [100, 200]
After appending
Appended HashSet: [50, 100, 20, 200, 10, 30]
```