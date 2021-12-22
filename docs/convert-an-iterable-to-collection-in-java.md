# 用 Java 将可迭代转换为集合

> 原文:[https://www . geesforgeks . org/convert-an-iterable-to-collection-in-Java/](https://www.geeksforgeeks.org/convert-an-iterable-to-collection-in-java/)

[](https://www.geeksforgeeks.org/java-implementing-iterator-and-iterable-interface/)**和 [**集合**](https://www.geeksforgeeks.org/collections-in-java-2/) 在 Java 中有很大的用处。迭代器在 Java 的 Collection 框架中用于逐个检索元素，Collection 是一组表示为单个单元的单个对象。Java 提供了集合框架，该框架定义了几个类和接口，将一组对象表示为一个单元。
但在某些时候，需要从 iterable 切换到 collection，反之亦然。关于 Iterable 和 Collection 区别的更多细节，请参考 Java 中 [**迭代器 vs Collection**](https://www.geeksforgeeks.org/iterator-vs-collection-in-java/)的帖子。
Iterable 向 Collection 的转换可以通过以下方式进行:** 

*   ****创建一个实用函数**:创建一个实用函数意味着创建一个函数，通过显式地考虑每个项目，将 iterable 转换为集合。这也可以通过多种方式实现，如下所述:

    *   **使用 For 循环**** 

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Below is the program to convert an Iterable
// into a Collection using for loop

import java.io.*;
import java.util.*;

class GFG {
    // function to convert Iterable into Collection
    public static <T> Collection<T>
                   getCollectionFromIterable(Iterable<T> itr)
    {
        // Create an empty Collection to hold the result
        Collection<T> cltn = new ArrayList<T>();

        // Iterate through the iterable to
        // add each element into the collection
        for (T t : itr)
            cltn.add(t);

        // Return the converted collection
        return cltn;
    }

    public static void main(String[] args)
    {
        Iterable<Integer> i = Arrays.asList(1, 2, 3, 4);
        System.out.println("Iterable List : " + i);

        Collection<Integer> cn = getCollectionFromIterable(i);
        System.out.println("Collection List : " + cn);
    }
}
```

****Output:** 

```java
Iterable List : [1, 2, 3, 4]
Collection List : [1, 2, 3, 4]
```** 

*   ****使用 Iterable.forEach()** :
    可用于 Java 8 及以上版本。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Below is the program to convert an Iterable
// into a Collection using iterable.forEach

import java.io.*;
import java.util.*;

class GFG {
    // function to convert Iterable into Collection
    public static <T> Collection<T>
                getCollectionFromIterable(Iterable<T> itr)
    {
        // Create an empty Collection to hold the result
        Collection<T> cltn = new ArrayList<T>();

        // Use iterable.forEach() to
        // Iterate through the iterable and
        // add each element into the collection
        itr.forEach(cltn::add);

        // Return the converted collection
        return cltn;
    }

    public static void main(String[] args)
    {
        Iterable<Integer> i = Arrays.asList(1, 2, 3, 4);
        System.out.println("Iterable List : " + i);

        Collection<Integer> cn = getCollectionFromIterable(i);
        System.out.println("Collection List : " + cn);
    }
}
```

****Output:** 

```java
Iterable List : [1, 2, 3, 4]
Collection List : [1, 2, 3, 4]
```** 

*   ****使用迭代器**:forEach 循环在后台使用迭代器。因此，它可以通过以下方式显式完成。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Below is the program to convert an Iterable
// into a Collection using Iterator

import java.io.*;
import java.util.*;

class GFG {
    // function to convert Iterable into Collection
    public static <T> Collection<T>
                   getCollectionFromIterable(Iterable<T> itr)
    {
        // Create an empty Collection to hold the result
        Collection<T> cltn = new ArrayList<T>();

        // Get the iterator at the iterable
        Iterator<T> iterator = itr.iterator();

        // Iterate through the iterable using
        // iterator to add each element into the collection
        while (iterator.hasNext()) {
            cltn.add(iterator.next());
        }

        // Return the converted collection
        return cltn;
    }

    public static void main(String[] args)
    {
        Iterable<Integer> i = Arrays.asList(1, 2, 3, 4);
        System.out.println("Iterable List : " + i);

        Collection<Integer> cn = getCollectionFromIterable(i);
        System.out.println("Collection List : " + cn);
    }
}
```

****Output:** 

```java
Iterable List : [1, 2, 3, 4]
Collection List : [1, 2, 3, 4]
```** 

*   ****Java 8 Stream** :随着 Java 8 中 [Stream 的引入，这样的作品已经变得相当容易了。要将可迭代转换为集合，首先将**可迭代**转换为**分裂器**。然后借助 **StreamSupport.stream()** 可以遍历分割器，然后借助 **collect()** 进行收集。](https://www.geeksforgeeks.org/stream-in-java/)**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Program to convert an Iterable
// into a Collection

import java.io.*;
import java.util.*;
import java.util.stream.*;

class GFG {
    // function to convert Iterable into Collection
    public static <T> Collection<T>
                    getCollectionFromIterable(Iterable<T> itr)
    {
        // Create an empty Collection to hold the result
        Collection<T> cltn = new ArrayList<T>();

        return StreamSupport.stream(itr.spliterator(), false)
            .collect(Collectors.toList());
    }

    public static void main(String[] args)
    {
        Iterable<Integer> i = Arrays.asList(1, 2, 3, 4);
        System.out.println("Iterable List : " + i);

        Collection<Integer> cn = getCollectionFromIterable(i);
        System.out.println("Collection List : " + cn);
    }
}
```

****Output:** 

```java
Iterable List : [1, 2, 3, 4]
Collection List : [1, 2, 3, 4]
```**