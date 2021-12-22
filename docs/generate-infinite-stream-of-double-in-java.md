# 在 Java 中生成无限双流

> 原文:[https://www . geeksforgeeks . org/generate-无限双入流 java/](https://www.geeksforgeeks.org/generate-infinite-stream-of-double-in-java/)

给定的任务是在 Java 中生成一个无限顺序的无序双流。

这可以通过以下方式实现:

*   **Using DoubleStream.iterate()**:
    1.  使用 DoubleStream.iterate()方法，通过将值增加 1 来用 I 迭代 DoubleStream。
    2.  借助 forEach()方法打印双流。

    ```java
    import java.util.stream.*;

    public class GFG {

        // Main method
        public static void main(String[] args)
        {

            DoubleStream

                // Iterate the DoubleStream with i
                // by incrementing the value with 1
                .iterate(0, i -> i + 1)

                // Print the DoubleStream
                // using forEach() method.
                .forEach(System.out::println);
        }
    }
    ```

    **输出:**

    ```java
    0.0
    1.0
    2.0
    3.0
    4.0
    5.0
    6.0
    .
    .
    .

    ```

*   **Using Random.doubles()**:
    1.  使用 doubles()方法获取下一个双精度值
    2.  借助 forEach()方法打印双流。

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

                // Get the next double
                // using doubles() method
                .doubles()

                // Print the DoubleStream
                // using forEach() method.
                .forEach(System.out::println);
        }
    }
    ```

    **输出:**

    ```java
    0.3668625445505631
    0.4385898887922953
    0.23333911864591927
    0.7134958163360963
    0.6945667694181287
    0.6898427735417596
    0.9243923588584183
    .
    .
    .

    ```

*   **Using DoubleStream.generate() method**:
    1.  使用 DoubleStream.generate()和 Random.nextDouble()生成下一个双精度值
    2.  借助 forEach()方法打印双流。

    ```java
    import java.util.stream.*;
    import java.util.*;

    public class GFG {

        // Main method
        public static void main(String[] args)
        {

            // Create a Random object
            Random random = new Random();

            DoubleStream

                // Generate the next double
                // using DoubleStream.generate()
                // and Random.nextDouble()
                .generate(random::nextDouble)

                // Print the DoubleStream
                // using forEach() method.
                .forEach(System.out::println);
        }
    }
    ```

    **输出:**

    ```java
    0.025801080723973246
    0.5115037630832635
    0.030815898624858784
    0.5441584143944648
    0.6984267528746901
    0.5821292304544626
    .
    .
    .

    ```