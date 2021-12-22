# Java 中的 Stream.of()和 Arrays.stream()方法的区别

> 原文:[https://www . geesforgeks . org/流和数组的区别-流-方法-java/](https://www.geeksforgeeks.org/difference-between-stream-of-and-arrays-stream-method-in-java/)

### Arrays.stream()

Java 中**数组类**的**流(T[]数组)**方法用于从作为参数传递的数组及其元素中获取一个顺序流。它返回一个顺序流，数组的元素作为参数传递，作为它的源。

**示例:**

```java
// Java program to demonstrate Arrays.stream() method

import java.util.*;
import java.util.stream.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a String array
        String[] arr = { "Geeks", "for", "Geeks" };

        // Using Arrays.stream() to convert
        // array into Stream
        Stream<String> stream = Arrays.stream(arr);

        // Displaying elements in Stream
        stream.forEach(str -> System.out.print(str + " "));
    }
}
```

### (的)流

**流(T…值)**返回一个顺序的有序流，其元素是指定的值。Stream.of()方法只是为非基元类型调用 Arrays.stream()方法。

**示例:**

```java
// Java code for Stream of(T... values)
// to get a sequential ordered stream whose
// elements are the specified values.

import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an Stream
        Stream stream = Stream.of("Geeks", "for", "Geeks");

        // Displaying the sequential ordered stream
        stream.forEach(str -> System.out.print(str + " "));
    }
}
```

这两种方法是从指定数组创建顺序流时最常用的两种方法。当用非基元类型 t 调用时，这两种方法都返回一个流

【Arrays.stream()和 Stream.of()之间的差异

即使()的 Stream.of 是 Arrays.stream()方法的包装器，也有一些特定的差异点，明确了何时使用 Arrays.stream()或何时使用 Stream.of()。以下是上述两种方法之间的一些区别:

1.  **Different return types**:

    对于基元数组(如 int[]、long[]等)，Arrays.stream()和 Stream.of()具有不同的返回类型。

    **示例:**传递一个整数数组，Stream.of()方法返回 Stream <int>，而 Arrays.stream()返回一个 IntStream。</int>

    ```java
    // Java program to demonstrate return type
    // of Arrays.stream() and Stream.of() method
    // for primitive arrays

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        public static void main(String[] args)
        {
            // Creating an integer array
            int arr[] = { 1, 2, 3, 4, 5 };

            // --------- Using Arrays.stream() ---------

            // to convert int array into Stream
            IntStream intStream = Arrays.stream(arr);

            // Displaying elements in Stream
            intStream.forEach(str -> System.out.print(str + " "));

            // --------- Using Stream.of() ---------

            // to convert int array into Stream
            Stream<int[]> stream = Stream.of(arr);

            // Displaying elements in Stream
            stream.forEach(str -> System.out.print(str + " "));
        }
    }
    ```

2.  **Stream.of()需要展平，而 Arrays.stream()不需要** :

    因为用于处理基元类型的流的理想类是它们的基元流类型(如 IntStream、LongStream 等)。因此，在使用之前，需要将()的流显式展平为其原始流。

    **示例:**

    ```java
    // Java program to demonstrate need of flattenning
    // Stream.of() method returned type for primitive arrays

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        public static void main(String[] args)
        {
            // Creating an integer array
            int arr[] = { 1, 2, 3, 4, 5 };

            // --------- Using Arrays.stream() ---------

            // to convert int array into Stream
            IntStream intStream = Arrays.stream(arr);

            // Displaying elements in Stream
            intStream.forEach(str -> System.out.print(str + " "));

            // --------- Using Stream.of() ---------

            // to convert int array into Stream
            Stream<int[]> stream = Stream.of(arr);

            // ***** Flattening of Stream<int[]> into IntStream *****

            // flattenning Stream<int[]> into IntStream
            // using flatMapToInt()
            IntStream intStreamNew = stream.flatMapToInt(Arrays::stream);

            // Displaying elements in IntStream
            intStreamNew.forEach(str -> System.out.print(str + " "));
        }
    }
    ```

3.  **stream . of()是泛型，而 Arrays.stream 不是** :

    Arrays.stream()方法只适用于 int[]、long[]、double[]类型的基元数组，并分别返回 IntStream、LongStream、DoubleStream。对于其他基本类型，Arrays.stream()不起作用。
    另一方面，()的流返回一个类型为 T 的通用流(流<t>)。因此，它可以用于任何类型。</t>

    **示例:**

    *   **For arrays . stream()方法:**

        ```java
        // Java program to demonstrate return type
        // of Arrays.stream() method
        // for primitive arrays of char

        import java.util.*;
        import java.util.stream.*;

        class GFG {

            public static void main(String[] args)
            {
                // Creating a character array
                char arr[] = { '1', '2', '3', '4', '5' };

                // --------- Using Arrays.stream() ---------
                // This will throw error

                // to convert char array into Stream
                Arrays.stream(arr);
            }
        }
        ```

        **输出:**

        > Java 代码中的编译错误:-
        > prog.java:20:错误:未找到适合 stream(char[])
        > arrays . stream(arr)；
        > ^

    *   **is the mainstay () method:**

        ```java
        // Java program to demonstrate return type
        // of Stream.of() method
        // for primitive arrays of char

        import java.util.*;
        import java.util.stream.*;

        class GFG {

            public static void main(String[] args)
            {
                // Creating a character array
                char arr[] = { '1', '2', '3', '4', '5' };

                // --------- Using Stream.of() ---------
                // Will work efficiently

                // to convert int array into Stream
                Stream<char[]> stream = Stream.of(arr);

                // Displaying elements in Stream
                stream.forEach(str -> System.out.print(str + " "));
            }
        }
        ```