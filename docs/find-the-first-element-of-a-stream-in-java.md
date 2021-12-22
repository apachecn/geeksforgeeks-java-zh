# 在 Java 中找到一个流的第一个元素

> 原文:[https://www . geeksforgeeks . org/find-Java 流中的第一个元素/](https://www.geeksforgeeks.org/find-the-first-element-of-a-stream-in-java/)

给定一个包含一些元素的**流**，任务是在 Java 中获取[流的第一个元素。](https://www.geeksforgeeks.org/stream-in-java/)

**示例:**

> **输入:**流= {“极客 _ 第一”、“极客 _2”、“极客 _3”、“极客 _4”、“极客 _ 最后”}
> **输出:**极客 _ 第一
> 
> **输入:**流= {1，2，3，4，5，6，7}
> **输出:** 1

有许多方法可以找到[流](https://www.geeksforgeeks.org/stream-in-java/)中的第一个元素:

1.  **Using [Stream.reduce()](https://www.geeksforgeeks.org/stream-reduce-java-examples/) Method:** The reduce method works on two elements in the stream and returns the element as per the required condition. Therefore this method can be used to reduce the stream so that it contains only the first element.

    **进场:**

    *   获取要返回第一个元素的元素流。
    *   要获得第一个元素，可以使用 **reduce()** 方法忽略第二个元素，重复操作，直到没有第二个元素。

        ```java
        Stream.reduce((first, second) -> first)

        ```

    *   这将流中的一组元素减少为单个元素，即*优先*。
    *   因此，唯一的单个元素将保留在流中，即第一个元素。

    以下是上述方法的实现:
    **示例:**

    ```java
    // Java program to find first
    // element of a Stream in Java

    import java.util.*;
    import java.util.stream.*;

    public class GFG {

        // Function to find the
        // first_elements in a Stream
        public static <T> T
        firstElementInStream(Stream<T> stream)
        {
            T first_element
                = stream

                      // reduce() method reduces the Stream
                      // to a single element, which is first.
                      .reduce((first, second) -> first)

                      // if stream is empty
                      // null is returned
                      .orElse(null);

            return first_element;
        }

        // Driver code
        public static void main(String[] args)
        {

            Stream<String> stream
                = Stream.of("Geek_First", "Geek_2",
                            "Geek_3", "Geek_4",
                            "Geek_Last");

            // Print the first element of a Stream
            System.out.println(
                "First Element: "
                + firstElementInStream(stream));
        }
    }
    ```

    **Output:**

    ```java
    First Element: Geek_First

    ```

2.  **Using Stream [findFirst()](https://www.geeksforgeeks.org/stream-findfirst-java-examples/) Method:** The **findFirst()** method will returns the first element of the stream or an empty if the stream is empty.

    **进场:**

    *   获取要返回第一个元素的元素流。
    *   要获取第一个元素，可以直接使用 **findFirst()** 方法。

        ```java
        Stream.findFirst()
        ```

    *   这将返回流的第一个元素。

    以下是上述方法的实现:
    **示例:**

    ```java
    // Java program to find first
    // element of a Stream in Java

    import java.util.*;
    import java.util.stream.*;

    public class GFG {

        // Function to find the
        // first_elements in a Stream
        public static <T> T
        firstElementInStream(Stream<T> stream)
        {
            T first_element
                = stream

                      // findFirst() method returns
                      // the first element of stream
                      .findFirst()

                      // if stream is empty
                      // null is returned
                      .orElse(null);

            return first_element;
        }

        // Driver code
        public static void main(String[] args)
        {

            Stream<String> stream
                = Stream.of("Geek_First", "Geek_2",
                            "Geek_3", "Geek_4",
                            "Geek_Last");

            // Print the first element of a Stream
            System.out.println(
                "First Element: "
                + firstElementInStream(stream));
        }
    }
    ```

    **Output:**

    ```java
    First Element: Geek_First

    ```