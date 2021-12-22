# 如何在 Java 中循环遍历 TreeSet？

> 原文:[https://www . geesforgeks . org/how-to-loop-over-treeset-in-Java/](https://www.geeksforgeeks.org/how-to-loop-over-treeset-in-java/)

TreeSet 是 Java 中 [SortedSet 接口](https://www.geeksforgeeks.org/sortedset-java-examples/)最重要的实现之一，它使用[树](https://www.geeksforgeeks.org/binary-tree-data-structure/)进行存储。无论是否提供明确的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)，元素的顺序都由一组使用它们的自然顺序来维护。如果要正确实现[设置界面](https://www.geeksforgeeks.org/set-in-java/)，这必须与 equals 一致。

现在的任务是探索有多少种方法可以在 TreeSet 上循环。众所周知 [TreeSet](https://www.geeksforgeeks.org/treeset-in-java/) 提供了 SortedSet 接口的实现，SortedSet 扩展了 Set 接口。它的行为就像一个简单的集合，只是它以排序的格式存储元素。

![](img/31b0e27f7605fef98b55045c08b0df6c.png)

以下是与 TreeSet 相关的一些特征，如下所示:

*   TreeSet 使用树形数据结构进行存储。
*   对象以排序的升序存储。但是我们可以使用方法 TreeSet.descendingIterator()以降序进行迭代。
*   访问和检索时间非常快，这使得 TreeSet 成为以排序格式存储大量数据的绝佳选择。
*   TreeSet 不使用 hashCode()和 equals()方法来比较它的元素。它使用 compare()(或 compareTo())方法来确定两个元素的相等性。

### 方法:

下面我们列出了在 java 中迭代 TreeSet 的各种方法，我们将进一步讨论这些方法，并将为以下每种方法提供一个干净的 java 程序:

1.  使用增强的 For 循环
2.  使用迭代器
3.  使用流(从 Java8 开始)

**方法 1:** 使用增强 For 循环

增强的 For 循环可用于以下列方式在树集上循环。

**语法:**

```java
for (Integer value : ts)
{
    System.out.print(value);
}
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Loop over TreeSet
// Using Enhanced For loop

// Importing required classes 
import java.util.Iterator;
import java.util.TreeSet;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeSet by
        // declaring object of TreeSet class of Integer type
        TreeSet<Integer> ts = new TreeSet<Integer>();

        // Adding elements to above TreeSet object
        ts.add(10);
        ts.add(61);
        ts.add(87);
        ts.add(39);

        // Display message for better readability
        System.out.print("TreeSet: ");

        // Looping over the TreeSet values
        for (Integer value : ts)

            // Print the values
            System.out.print(value + ", ");

        System.out.println();
    }
}
```

**Output**

```java
TreeSet: 10, 39, 61, 87, 
```

**方法 2:** 使用迭代器

迭代器可以在 TreeSet 对象上创建。因此，这个迭代器可以用来遍历或循环树集。

**语法:**

```java
Iterator iterator = ts.iterator();

while (iterator.hasNext())
{
System.out.print(iterator.next());
}
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to loop over TreeSet
// Using Iterator

// Importing required classes
import java.util.Iterator;
import java.util.TreeSet;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeSet by
        // declaring an object of TreeSet class
        TreeSet<Integer> ts = new TreeSet<Integer>();

        // Adding elements to above object of TreeSet class
        // Using add() method
        ts.add(10);
        ts.add(61);
        ts.add(87);
        ts.add(39);

        // Create an Iterator over the TreeSet
        Iterator<Integer> iterator = ts.iterator();

        // Display message for better readability
        System.out.print("TreeSet: ");

        // Looping over the TreeSet values
        while (iterator.hasNext())

            // Print all the values inside TreeSet object
            System.out.print(iterator.next() + ", ");

        System.out.println();
    }
}
```

**方法三:使用 Java 8 forEach / stream** :

Java 8 forEach / stream 可以用下面的方式在 TreeSet 上循环。

**语法:**

```java
Tree_Set.forEach(iterator -> System.out.print(i + " "));
// Using forEach 
```

```java
Tree_Set.stream().map(iterator -> String.valueOf(i)).collect(Collectors.joining(", "))
// Using stream  
```

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to loop over TreeSet
// Using For-each and Stream in Java8

// Importing required classes
import java.util.Arrays;
import java.util.Iterator;
import java.util.TreeSet;
import java.util.stream.Collectors;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeSet if integer type
        TreeSet<Integer> ts = new TreeSet<Integer>();

        // Adding elements to the TreeSet
        // using addAll() method
        ts.addAll(Arrays.asList(10, 61, 87, 39));

        // Looping over the TreeSet & print values
        System.out.print("TreeSet without Comma: ");

        // Iterating through the TreeSet
        // using forEach
        ts.forEach(i -> System.out.print(i + " "));
        System.out.println();

        // Looping over the TreeSet & print values
        System.out.print("TreeSet with Comma: ");

        // Iterating through the TreeSet
        // Using stream concept introduced in Java8
        System.out.print(
            ts.stream()
                .map(i -> String.valueOf(i))
                .collect(Collectors.joining(", ")));
    }
}
```

**Output**

```java
TreeSet without Comma: 10 39 61 87 
TreeSet with Comma: 10, 39, 61, 87
```