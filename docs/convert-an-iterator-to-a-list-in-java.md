# 用 Java 将迭代器转换为列表

> 原文:[https://www . geesforgeks . org/convert-a-iterator-a-list-in-Java/](https://www.geeksforgeeks.org/convert-an-iterator-to-a-list-in-java/)

给定一个迭代器，任务是将其转换为 Java 中的列表。

**示例:**

```
Input: Iterator = {1, 2, 3, 4, 5}
Output: {1, 2, 3, 4, 5}

Input: Iterator = {'G', 'e', 'e', 'k', 's'}
Output: {'G', 'e', 'e', 'k', 's'}

```

以下是各种方法:

*   **Naive Approach**:
    1.  获取迭代器。
    2.  创建一个空列表。
    3.  使用 forEachRemaining()方法将迭代器的每个元素添加到列表中。
    4.  退回清单。

    下面是上述方法的实现:

    ```
    // Java program to get a List
    // from a given Iterator

    import java.util.*;

    class GFG {

        // Function to get the List
        public static <T> List<T>
        getListFromIterator(Iterator<T> iterator)
        {

            // Create an empty list
            List<T> list = new ArrayList<>();

            // Add each element of iterator to the List
            iterator.forEachRemaining(list::add);

            // Return the List
            return list;
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the Iterator
            Iterator<Integer>
                iterator = Arrays.asList(1, 2, 3, 4, 5)
                               .iterator();

            // Get the List from the Iterator
            List<Integer>
                list = getListFromIterator(iterator);

            // Print the list
            System.out.println(list);
        }
    }
    ```

    **Output:**

    ```
    [1, 2, 3, 4, 5]

    ```

*   **Using Iterable as intermediate**:
    1.  获取迭代器。
    2.  使用 lambda 表达式将迭代器转换为可迭代的。
    3.  使用流将可列表转换为列表。
    4.  退回清单。

    下面是上述方法的实现:

    ```
    // Java program to get a List
    // from a given Iterator

    import java.util.*;
    import java.util.stream.Collectors;
    import java.util.stream.StreamSupport;

    class GFG {

        // Function to get the List
        public static <T> List<T>
        getListFromIterator(Iterator<T> iterator)
        {

            // Convert iterator to iterable
            Iterable<T> iterable = () -> iterator;

            // Create a List from the Iterable
            List<T> list = StreamSupport
                               .stream(iterable.spliterator(), false)
                               .collect(Collectors.toList());

            // Return the List
            return list;
        }

        // Driver code
        public static void main(String[] args)
        {

            // Get the Iterator
            Iterator<Integer>
                iterator = Arrays.asList(1, 2, 3, 4, 5)
                               .iterator();

            // Get the List from the Iterator
            List<Integer>
                list = getListFromIterator(iterator);

            // Print the list
            System.out.println(list);
        }
    }
    ```

    **Output:**

    ```
    [1, 2, 3, 4, 5]

    ```