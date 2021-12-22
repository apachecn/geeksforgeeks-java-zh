# 用 Java 创建流的 10 种方法

> 原文:[https://www . geesforgeks . org/10-创建 java 流的方法/](https://www.geeksforgeeks.org/10-ways-to-create-a-stream-in-java/)

Java 8 中引入的[流 API](https://www.geeksforgeeks.org/stream-in-java/) ，用于处理对象的集合。Stream 是一个对象序列，它支持许多不同的方法，这些方法可以通过管道排列来产生所需的结果。

Java 流的特点是–

*   流不是数据结构，而是从集合、数组或输入/输出通道获取输入。
*   流不改变原始数据结构，它们只提供流水线方法的结果。
*   每个中间操作都被延迟执行，并返回一个流，因此各种中间操作都可以用管道连接。终端操作标记流的结尾并返回结果。

**创建流的不同方式:**

1.  **Using [Collection](https://www.geeksforgeeks.org/collections-in-java-2/)**

    **进场:**

    1.  获取收藏
    2.  使用 Collection.stream()方法从集合中构造一个顺序流
    3.  打印流

    下面是上述方法的实现:

    **程序:**

    ```
    // Java program to create Stream from Collections

    import java.util.*;
    import java.util.stream.Stream;

    class GFG {

        // Function convert a List into Stream
        private static <T> void getStream(List<T> list)
        {

            // Create stream object with the List
            Stream<T> stream = list.stream();

            // Iterate list first to last element
            Iterator<T> it = stream.iterator();

            // Iterate stream object
            while (it.hasNext()) {
                System.out.print(it.next() + " ");
            }
        }

        public static void main(String[] args)
        {

            // Create ArrayList of String
            List<String> list = new ArrayList<>();

            // Add element in list
            list.add("Geeks");
            list.add("for");
            list.add("Geeks");

            // Get the Stream from the List
            getStream(list);
        }
    }
    ```

    **Output:**

    ```
    Geeks for Geeks

    ```

2.  **Create a stream from specified values**

    **[Stream.of(T…t)](https://www.geeksforgeeks.org/stream-oft-values-java-examples/)** 方法可用于创建具有指定 T 值的流，其中 T 是元素。这个方法返回一个包含 t 个元素的顺序流。

    下面是上述方法的实现:

    **程序:**

    ```
    // Java program to create Stream from values

    import java.util.*;
    import java.util.stream.Stream;

    class GFG {

        // Function convert a List into Stream
        private static void getStream()
        {

            // Create a stream from specified values
            Stream<Integer> stream
                = Stream.of(1, 2,
                            3, 4,
                            5, 6,
                            7, 8,
                            9);

            // Displaying the sequential ordered stream
            stream.forEach(p -> System.out.print(p + " "));
        }

        public static void main(String[] args)
        {

            // Get the Stream from the values
            getStream();
        }
    }
    ```

    **Output:**

    ```
    1 2 3 4 5 6 7 8 9

    ```

3.  **Create stream from an array:**

    ()流和数组流是从指定数组创建顺序流的两种常用方法。当用非基元类型的整数数组调用时，这两个方法都返回一个流

    *   **Create stream using [Arrays.stream()](https://www.geeksforgeeks.org/arrays-stream-method-in-java/)**

        **程序:**

        ```
        // Java program to create Stream from Collections

        import java.util.*;
        import java.util.stream.Stream;

        class GFG {

            // Function convert a List into Stream
            private static <T> void getStream(T[] arr)
            {

                // Create stream from an array
                // using Arrays.stream()
                Stream<T> streamOfArray
                    = Arrays.stream(arr);

                // Iterate list first to last element
                Iterator<T> it
                    = streamOfArray.iterator();

                // Iterate stream object
                while (it.hasNext()) {
                    System.out.print(it.next() + " ");
                }
            }

            public static void main(String[] args)
            {

                // Get the array
                String[] arr
                    = new String[] { "a", "b", "c" };

                // Get the Stream from the Array
                getStream(arr);
            }
        }
        ```

        **Output:**

        ```
        a b c

        ```

    *   **Create stream using [Stream.of()](https://www.geeksforgeeks.org/stream-oft-t-java-examples/)**
        A non interfering action to be perform on elements as they are consumed from the stream and returns also a new stream.

        **程序:**

        ```
        // Java program to create Stream from Collections

        import java.util.*;
        import java.util.stream.Stream;

        class GFG {

            // Function convert a List into Stream
            private static <T> void getStream(T[] arr)
            {

                // Create stream from an array
                // using Stream.of()
                Stream<T> streamOfArray = Stream.of(arr);

                // Iterate list first to last element
                Iterator<T> it = streamOfArray.iterator();

                // Iterate stream object
                while (it.hasNext()) {
                    System.out.print(it.next() + " ");
                }
            }

            public static void main(String[] args)
            {

                // Get the array
                String[] arr
                    = new String[] { "a", "b", "c" };

                // Get the Stream from the Array
                getStream(arr);
            }
        }
        ```

        **Output:**

        ```
        a b c

        ```

4.  **Create an empty stream using [Stream.empty()](https://www.geeksforgeeks.org/stream-empty-java-examples/)**

    空()方法在创建时使用，以避免为没有元素的流返回 null。

    **程序:**

    ```
    // Java program to create empty Stream

    import java.util.*;
    import java.util.stream.Stream;

    class GFG {

        // Function convert a List into Stream
        private static void getStream()
        {

            // Create stream from an array using Stream.empty()
            Stream<String> streamOfArray
                = Stream.empty();

            // Iterate list first to last element
            Iterator<String> it
                = streamOfArray.iterator();

            // Iterate stream object
            while (it.hasNext()) {
                System.out.print(it.next() + " ");
            }
        }

        public static void main(String[] args)
        {

            // Get the empty Stream
            getStream();
        }
    }
    ```

    **Output:**
5.  **Create a Stream using [Stream.builder()](https://www.geeksforgeeks.org/stream-builder-java-examples/)**

    当应该在语句的右边部分另外指定所需的类型时，使用 builder()方法，否则 build()方法将创建流的实例。

    **程序:**

    ```
    // Java program to create Stream from Collections

    import java.util.*;
    import java.util.stream.Stream;

    class GFG {

        // Function convert a List into Stream
        private static <T> void getStream()
        {

            // Create stream using Stream builder()
            Stream.Builder<String> builder
                = Stream.builder();

            // Adding elements in the stream of Strings
            Stream<String> stream = builder.add("a")
                                        .add("b")
                                        .add("c")
                                        .build();

            // Iterate list first to last element
            Iterator<String> it = stream.iterator();

            // Iterate stream object
            while (it.hasNext()) {
                System.out.print(it.next() + " ");
            }
        }

        public static void main(String[] args)
        {

            // Get the Stream using Builder
            getStream();
        }
    }
    ```

    **Output:**

    ```
    a b c

    ```

6.  **Create an infinite Stream using Stream.iterate()**

    iterate()方法返回一个无限顺序有序流，该流是通过对初始元素种子迭代应用函数 f 而产生的。在下面的示例中，结果流的第一个元素是迭代方法的第一个参数。为了创建每一个后续元素，该函数应用于前一个元素。在下面的例子中，第二个元素是 4。

    **程序:**

    ```
    // Java program to create infinite Stream
    // using Stream.iterate() method

    import java.util.*;
    import java.util.stream.Stream;

    class GFG {

        // Function convert a List into Stream
        private static <T> void
        getStream(int seedValue, int limitTerms)
        {

            // Create infinite stream
            // using Stream.iterate() method
            Stream.iterate(seedValue,
                           (Integer n) -> n * n)
                .limit(limitTerms)
                .forEach(System.out::println);
        }

        public static void main(String[] args)
        {

            // Get the seed value
            int seedValue = 2;

            // Get the limit for number of terms
            int limitTerms = 5;

            // Get the Stream from the function
            getStream(seedValue, limitTerms);
        }
    }
    ```

    **Output:**

    ```
    2
    4
    16
    256
    65536

    ```

7.  **Create an infinite Stream using [Stream.generate()](https://www.geeksforgeeks.org/stream-generate-method-java/) method**

    generate()方法接受一个供应商来生成元素，生成的流是无限的。因此，要限制它，请指定所需的大小，否则 generate()方法将一直工作，直到达到内存限制。

    **程序:**

    ```
    // Java program to create infinite Stream
    // using Stream.generate() method

    import java.util.*;
    import java.util.stream.*;

    class GFG {

        // Function convert a List into Stream
        private static <T> void getStream(int limitTerms)
        {

            // Create infinite stream
            // using Stream.generate() method
            Stream.generate(Math::random)
                .limit(limitTerms)
                .forEach(System.out::println);
        }

        public static void main(String[] args)
        {

            // Get the limit for number of terms
            int limitTerms = 5;

            // Get the Stream from the function
            getStream(limitTerms);
        }
    }
    ```

    **Output:**

    ```
    0.2293502475696314
    0.5650334795948209
    0.3418138293253522
    0.36831074763500116
    0.4864408670097241

    ```

8.  **Create stream from a [Pattern](https://www.geeksforgeeks.org/regular-expressions-in-java/) using [Predicate](https://www.geeksforgeeks.org/java-8-predicate-with-examples/)**

    在 java 8 中，Pattern 的谓词 asPredicate()方法创建了一个用于模式匹配的谓词布尔值函数。

    **程序:**

    ```
    // Java program to create Stream from Collections

    import java.util.*;
    import java.util.stream.*;
    import java.util.regex.Pattern;

    class GFG {

        // Function convert a List into Stream
        private static void
        getStream(List<String> list, Pattern p)
        {

            list.stream()
                .filter(p.asPredicate())
                .forEach(System.out::println);
        }

        public static void main(String[] args)
        {

            // Create ArrayList of String
            // that is backed by the specified array
            List<String> list
                = Arrays
                      .asList("Geeks",
                              "For",
                              "Geek",
                              "GeeksForGeeks",
                              "A Computer Portal");

            // Get the pattern
            Pattern p = Pattern.compile("^G");

            // Get the Stream from the List matching Pattern
            getStream(list, p);
        }
    }
    ```

    **Output:**

    ```
    Geeks
    Geek
    GeeksForGeeks

    ```