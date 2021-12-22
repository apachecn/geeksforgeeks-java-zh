# 在 Java 中将迭代器转换为可迭代的

> 原文:[https://www . geesforgeks . org/convert-iterator-to-iteratable-in-Java/](https://www.geeksforgeeks.org/convert-iterator-to-iterable-in-java/)

给定一个迭代器，任务是将其转换为 Java 中的 Iterables。

**示例:**

```java
Input: Iterator = {1, 2, 3, 4, 5}
Output: {1, 2, 3, 4, 5}

Input: Iterator = {'G', 'e', 'e', 'k', 's'}
Output: {'G', 'e', 'e', 'k', 's'}

```

以下是各种方法:

*   **By overriding the abstract method Iterable.iterator()**:
    1.  获取迭代器。
    2.  重写 Iterable.iterator()方法并获取 Iterable。
    3.  返回 Iterable。

    下面是上述方法的实现:

    ```java
    // Java program to get a Iterable
    // from a given Iterator

    import java.util.*;

    class GFG {

        // Function to get the Spliterator
        public static <T> Iterable<T>
        getIterableFromIterator(Iterator<T> iterator)
        {
            return new Iterable<T>() {
                @Override
                public Iterator<T> iterator()
                {
                    return iterator;
                }
            };
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the Iterator
            Iterator<Integer>
                iterator = Arrays.asList(1, 2, 3, 4, 5)
                               .iterator();

            // Get the Iterable from the Iterator
            Iterable<Integer>
                iterable = getIterableFromIterator(iterator);

            // Print the elements of Iterable
            iterable.forEach(System.out::println);
        }
    }
    ```

    **Output:**

    ```java
    1
    2
    3
    4
    5

    ```

*   **Using Java 8 lambda expression**:
    1.  获取迭代器。
    2.  使用 Lambda 表达式将迭代器转换为可迭代的。
    3.  返回 Iterable。

    下面是上述方法的实现:

    ```java
    // Java program to get an Iterable
    // from a given Iterator

    import java.util.*;

    class GFG {

        // Function to get the Spliterator
        public static <T> Iterable<T>
        getIterableFromIterator(Iterator<T> iterator)
        {
            return () -> iterator;
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the Iterator
            Iterator<Integer>
                iterator = Arrays.asList(1, 2, 3, 4, 5)
                               .iterator();

            // Get the Iterable from the Iterator
            Iterable<Integer>
                iterable = getIterableFromIterator(iterator);

            // Print the elements of Iterable
            iterable.forEach(System.out::println);
        }
    }
    ```

    **Output:**

    ```java
    1
    2
    3
    4
    5

    ```

*   **Using Spliterators**:
    1.  获取迭代器。
    2.  使用 spliterators . spliteratorrunknownsize()方法将迭代器转换为 Spliterator。
    3.  使用 StreamSupport.stream()方法将拆分器转换为顺序流。
    4.  使用 Collect()方法将顺序流的元素收集为可迭代的。
    5.  返回 Iterable。

    下面是上述方法的实现:

    ```java
    // Java program to get a Iterable
    // from a given Iterator

    import java.util.*;
    import java.util.stream.Collectors;
    import java.util.stream.StreamSupport;

    class GFG {

        // Function to get the Spliterator
        public static <T> Iterable<T>
        getIterableFromIterator(Iterator<T> iterator)
        {
            return StreamSupport

                // Convert the iterator into a Spliterator
                // and then into a sequential stream
                .stream(Spliterators.spliteratorUnknownSize(iterator, 0),
                        false)

                // Convert the stream to an iterable
                .collect(Collectors.toList());
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the Iterator
            Iterator<Integer>
                iterator = Arrays.asList(1, 2, 3, 4, 5)
                               .iterator();

            // Get the Iterable from the Iterator
            Iterable<Integer>
                iterable = getIterableFromIterator(iterator);

            // Print the elements of Iterable
            iterable.forEach(System.out::println);
        }
    }
    ```

    **Output:**

    ```java
    1
    2
    3
    4
    5

    ```