# Java 程序将迭代器转换为拆分器

> 原文:[https://www . geesforgeks . org/Java-程序-转换-迭代器-拆分器/](https://www.geeksforgeeks.org/java-program-to-convert-iterator-to-spliterator/)

给定一个迭代器，任务是将其转换为 Java 中的拆分器。

**例:**

```java
Input: Iterator = {1, 2, 3, 4, 5}
Output: {1, 2, 3, 4, 5}

Input: Iterator = {'G', 'e', 'e', 'k', 's'}
Output: {'G', 'e', 'e', 'k', 's'}

```

**方法:**

1.  Gets the iterator.
2.  Use spliterators. spliteratorunknownsize () method to convert iterators into splitters.
3.  Return to the splitter.

下面是上述方法的实现:

```java
// Java program to get a Spliterator
// from a given Iterator

import java.util.*;

class GFG {

    // Function to get the Spliterator
    public static <T> Spliterator<T>
    getSpliteratorFromIterator(Iterator<T> iterator)
    {
        return Spliterators
            .spliteratorUnknownSize(iterator, 0);
    }

    // Driver code
    public static void main(String[] args)
    {
        // Get the Iterator
        Iterator<Integer>
            iterator = Arrays.asList(1, 2, 3, 4, 5)
                           .iterator();

        // Get the Spliterator from the Iterator
        Spliterator<Integer>
            si = getSpliteratorFromIterator(iterator);

        // Print the elements of Spliterator
        si.forEachRemaining(System.out::println);
    }
}
```

**输出:**

```java
1
2
3
4
5

```