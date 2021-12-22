# 从列表容器中删除空值的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-程序-从列表中移除空值-容器/](https://www.geeksforgeeks.org/java-program-to-remove-nulls-from-a-list-container/)

[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)是对象的有序集合，允许按照插入顺序存储重复值或**空值**。因此，在许多情况下移除空值非常重要。

**示例:**

```java
Input:  [Geeks, null, forGeeks, null, A computer portal]
Output: [Geeks, forGeeks, A computer portal]

Input:  [1, null, 2, 3, null, 4]
Output: [1, 2, 3, 4]

```

以下是在 Java 中从列表中移除空值的方法:

1.  **Using List.remove()** List interface provides a pre-defined method **remove(element)** which is used to remove a single occurrence of the element passed, from the List, if found.

    **算法**:

    1.  获取具有空值的列表。
    2.  重复调用列表中的**移除(空)**，直到所有空值都被移除。
    3.  返回/打印列表(现在删除所有空值)。

    ```java
    // Java Program to remove nulls
    // from a List using List.remove()

    import java.util.*;

    class GFG {
        public static void main(String[] args)
        {

            // Create the list with null values
            List<String> list = new ArrayList<>(
                Arrays.asList("Geeks",
                              null,
                              "forGeeks",
                              null,
                              "A computer portal"));

            // Print the list
            System.out.println("Initial List: " + list);

            // Removing nulls using List.remove()
            // Repeatedly call remove() till all null are removed
            while (list.remove(null)) {
            }

            // Print the list
            System.out.println("Modified List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Initial List: [Geeks, null, forGeeks, null, A computer portal]
    Modified List: [Geeks, forGeeks, A computer portal]

    ```

2.  **Using List.removeAll()**: List interface provides another pre-defined method **removeAll(Collection)** which is used to remove all occurrences of the elements of the Collection passed, from the List, if found.

    **算法**:

    1.  获取具有空值的列表。
    2.  使用 **Collections.singletonList(空)**创建一个只包含空元素的集合
    3.  调用列表中的**移除所有(集合)**一次。
    4.  返回/打印列表(现在删除所有空值)。

    ```java
    // Java Program to remove nulls
    // from a List using List.removeAll()

    import java.util.*;

    class GFG {
        public static void main(String[] args)
        {

            // Create the list with null values
            List<String> list = new ArrayList<>(
                Arrays.asList("Geeks",
                              null,
                              "forGeeks",
                              null,
                              "A computer portal"));

            // Print the list
            System.out.println("Initial List: " + list);

            // Removing nulls using List.removeAll()
            // passing a collection with single element "null"
            list.removeAll(Collections.singletonList(null));

            // Print the list
            System.out.println("Modified List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Initial List: [Geeks, null, forGeeks, null, A computer portal]
    Modified List: [Geeks, forGeeks, A computer portal]

    ```

3.  **Using iterator**: [Iterator](https://www.geeksforgeeks.org/how-to-use-iterator-in-java/) is an interface which belongs to collection framework. It allows user to traverse the collection, access the data element and remove the data elements of the collection.

    **算法**:

    1.  获取具有空值的列表。
    2.  从列表中创建迭代器
    3.  使用创建的迭代器遍历列表的每个元素
    4.  检查每个元素是否为空。如果发现为空，对该元素调用 **IteratorElement.remove()** 。
    5.  返回/打印列表(现在删除所有空值)。

    **程序:**

    ```java
    // Java Program to remove nulls
    // from a List using iterator

    import java.util.*;

    class GFG {

        // Generic function to remove Null Using Iterator
        public static <T> List<T> removeNullUsingIterator(List<T> list)
        {

            // Create an iterator from the list
            Iterator<T> itr = list.iterator();

            // Find and remove all null
            while (itr.hasNext()) {
                if (itr.next() == null)
                    itr.remove(); // remove nulls
            }

            // Return the null
            return list;
        }

        public static void main(String[] args)
        {

            // Create the list with null values
            List<String> list = new ArrayList<>(
                Arrays.asList("Geeks",
                              null,
                              "forGeeks",
                              null,
                              "A computer portal"));

            // Print the list
            System.out.println("Initial List: " + list);

            // Removing nulls using iterator
            list = removeNullUsingIterator(list);

            // Print the list
            System.out.println("Modified List:  " + list);
        }
    }
    ```

    **Output:**

    ```java
    Initial List: [Geeks, null, forGeeks, null, A computer portal]
    Modified List:  [Geeks, forGeeks, A computer portal]

    ```

4.  **Using Guava Iterables removeIf()**: Guava Iterables class provides **Iterables.removeIf(Iterable, Predicate)** that removes every element from a specified Iterable (or Collections that implements Iterable) that satisfies the provided [predicate](https://www.geeksforgeeks.org/java-8-predicate-with-examples/).

    **算法**:

    1.  获取具有空值的列表。
    2.  获取谓词条件**谓词. isNull()** 以传入 removeIf()的参数
    3.  调用 **Iterables.removeIf(List，谓词)**其中 List 是带有空值的原始列表，谓词是谓词. isNull()实例。
    4.  返回/打印列表(现在删除所有空值)。

    ```java
    // Java Program to remove nulls
    // from a List using Guava Iterables

    import com.google.common.base.Predicates;
    import com.google.common.collect.Iterables;
    import java.util.*;

    class GFG {
        public static void main(String[] args)
        {

            // Create the list with null values
            List<String> list = new ArrayList<>(
                Arrays.asList("Geeks",
                              null,
                              "forGeeks",
                              null,
                              "A computer portal"));

            // Print the list
            System.out.println("Initial List: " + list);

            // Removing nulls using Guava Iterables
            // using Predicate condition isNull()
            Iterables.removeIf(list, Predicates.isNull());

            // Print the list
            System.out.println("Modified List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Initial List: [Geeks, null, forGeeks, null, A computer portal]
    Modified List: [Geeks, forGeeks, A computer portal]

    ```

5.  **Using Apache Commons Collections filter()**: Apache Commons Collections CollectionUtils class provides **filter(Iterable, Predicate)** that removes every element from a specified iterable that do not satisfies the provided [predicate](https://www.geeksforgeeks.org/java-8-predicate-with-examples/).

    **算法**:

    1.  获取具有空值的列表。
    2.  获取谓词条件**谓词. NotNull 谓词()**以传入 filter()的参数，这样通过条件 *NotNull* 的元素将保留在列表中，而所有其他元素都将被过滤。
    3.  调用 **CollectionUtils.filter(list，predicteutils . not nullpredicate())**其中 list 是带有空值的原始列表，predicteutils . not nullpredicate()实例是谓词。
    4.  返回/打印列表(现在删除所有空值)。

    **程序:**

    ```java
    // Java Program to remove nulls
    // from a List using Apache Common COllection Filter()
    import org.apache.commons.collections4.CollectionUtils;
    import org.apache.commons.collections4.PredicateUtils;
    import java.util.*;

    class GFG {
        public static void main(String[] args)
        {

            // Create the list with null values
            List<String> list = new ArrayList<>(
                Arrays.asList("Geeks",
                              null,
                              "forGeeks",
                              null,
                              "A computer portal"));

            // Print the list
            System.out.println("Initial List: " + list);

            // Removing nulls using Apache Common filter()
            // using Predicate condition notNullPredicate()
            CollectionUtils.filter(list, PredicateUtils.notNullPredicate());

            // Print the list
            System.out.println("Modified List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Initial List: [Geeks, null, forGeeks, null, A computer portal]
    Modified List: [Geeks, forGeeks, A computer portal]

    ```

6.  **Using Lambdas (Java 8)**: **Stream.filter()** method can be used in Java 8 that returns a stream consisting of the elements
    that match the given predicate condition.

    **算法**:

    1.  获取具有空值的列表。
    2.  使用**列表从列表中创建一个流**
    3.  使用**列表过滤不为空的元素流。= null)**
    4.  使用**将流作为列表收集回来。collect(Collectors.toList()**
    5.  返回/打印列表(现在删除所有空值)。

    ```java
    // Java Program to remove nulls
    // from a List using Apache Common COllection Filter()

    import java.util.stream.Collectors;
    import java.util.*;

    class GFG {
        public static void main(String[] args)
        {

            // Create the list with null values
            List<String> list = new ArrayList<>(
                Arrays.asList("Geeks",
                              null,
                              "forGeeks",
                              null,
                              "A computer portal"));

            // Print the list
            System.out.println("Initial List: " + list);

            // Removing nulls using Java Stream
            // using Predicate condition in lambda expression
            list = list.stream()
                       .filter(x -> x != null)
                       .collect(Collectors.toList());

            // Print the list
            System.out.println("Modified List: " + list);
        }
    }
    ```

    **Output:**

    ```java
    Initial List: [Geeks, null, forGeeks, null, A computer portal]
    Modified List: [Geeks, forGeeks, A computer portal]

    ```