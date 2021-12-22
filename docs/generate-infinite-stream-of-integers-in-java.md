# 在 Java 中生成无限的整数流

> 原文:[https://www . geesforgeks . org/generate-无限 java 整数流/](https://www.geeksforgeeks.org/generate-infinite-stream-of-integers-in-java/)

给定的任务是在 Java 中生成一个无限顺序的无序整数流。

这可以通过以下方式实现:

*   **Using IntStream.iterate()**:
    1.  使用 IntStream.iterate()方法，通过将值递增 1 来用 I 迭代 IntStream。
    2.  借助 forEach()方法打印输入流。

    ```java
    import java.util.stream.*;

    public class GFG {

        // Main method
        public static void main(String[] args)
        {

            IntStream

                // Iterate the IntStream with i
                // by incrementing the value with 1
                .iterate(0, i -> i + 1)

                // Print the IntStream
                // using forEach() method.
                .forEach(System.out::println);
        }
    }
    ```

    **输出:**

    ```java
    0
    1
    2
    3
    4
    5
    .
    .
    .

    ```

*   **Using Random.ints()**:
    1.  使用 ints()方法获取下一个整数
    2.  借助 forEach()方法打印输入流。

    ```java
    import java.util.stream.*;
    import java.util.*;

    public class GFG {

        // Main method
        public static void main(String[] args)
        {

            // Create a Random object
            Random random = new Random();

            random

                // Get the next integer
                // using ints() method
                .ints()

                // Print the IntStream
                // using forEach() method.
                .forEach(System.out::println);
        }
    }
    ```

    **输出:**

    ```java
    -1214876682
    911266110
    1224044471
    -1867062635
    1893822159
    1226183018
    741533414
    .
    .
    .

    ```

*   **Using IntStream.generate()**:
    1.  使用 IntStream.generate()和 Random.nextInt()生成下一个整数
    2.  借助 forEach()方法打印输入流。

    ```java
    import java.util.stream.*;
    import java.util.*;

    public class GFG {

        // Main method
        public static void main(String[] args)
        {

            // Create a Random object
            Random random = new Random();

            IntStream

                // Generate the next integer
                // using IntStream.generate()
                // and Random.nextInt()
                .generate(random::nextInt)

                // Print the IntStream
                // using forEach() method.
                .forEach(System.out::println);
        }
    }
    ```

    **输出:**

    ```java
    -798555363
    -531857014
    1861939261
    273120213
    -739170342
    1295941815
    870955405
    -631166457
    .
    .
    .

    ```