# 如何比较 Java 中的两个集合？

> 原文:[https://www . geesforgeks . org/如何比较两个 java 集合/](https://www.geeksforgeeks.org/how-to-compare-two-collections-in-java/)

Java **集合**提供了一个存储和操作对象组的架构。这里我们将看到如何在 Java 中比较集合中的元素。

**步骤:**

*   Get two inputs with the function of [aslist ()](https://www.geeksforgeeks.org/arrays-aslist-method-in-java-with-examples/) .
*   Use the [collections.sort ()](https://www.geeksforgeeks.org/collections-sort-java-examples/) method to sort them.
*   Use the [equals ()](https://www.geeksforgeeks.org/method-class-equals-method-in-java/) function for comparison.
*   Print out. (True means they are equal, false means they are different)

**例 1:**

## Java

```java
// Java program implementing
// Comparing elements of Collections

import java.util.*;
import java.io.*;

public class ArrayCompareExample {

    // main function accepting string arguments
    public static void main(String[] args)
    {
        // create listA
        ArrayList<String> listA
            = new ArrayList<>(Arrays.asList("a", "b", "c"));

        // create listB
        ArrayList<String> listB
            = new ArrayList<>(Arrays.asList("a", "b", "d"));

        // sorting both lists
        Collections.sort(listA);
        Collections.sort(listB);

        // Compare lists using
        // equals() method
        boolean isEqual = listA.equals(listB);

        // print output on screen (true or false)
        System.out.println(isEqual);
    }
}
```

**输出**

```java
false
```

**例 2:**

## Java

```java
// Java program implementing
// Comparing elements of Collections

import java.util.*;
import java.io.*;

public class ArrayCompareExample {

    // main function accepting string arguments
    public static void main(String[] args)
    {
        // create listA
        ArrayList<Integer> listA
            = new ArrayList<>(Arrays.asList(3, 4, 5));

        // create listB
        ArrayList<Integer> listB
            = new ArrayList<>(Arrays.asList(4, 5, 3));

        // sorting both lists
        Collections.sort(listA);
        Collections.sort(listB);

        // Compare lists using
        // equals() method
        boolean isEqual = listA.equals(listB);

        // print output on screen (true or false)
        System.out.println(isEqual);
    }
}
```

**输出**

```java
true
```