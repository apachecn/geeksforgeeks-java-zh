# LongStream。Java 中的 Builder add(长 t)

> 原文:[https://www . geesforgeks . org/longstream-builder-addlong-t-in-Java/](https://www.geeksforgeeks.org/longstream-builder-addlong-t-in-java/)

**LongStream。Builder add(long t)** 用于在 stream 的构建阶段将元素插入到元素中。它向正在构建的流中添加一个元素。

**语法:**

```
default LongStream.Builder add(long t)
```

**参数:**该方法接受一个强制参数 **t** ，它是输入到流中的元素。

**异常:**当构建器已经转换到构建状态时，该方法抛出**非法状态异常**。这意味着该流已经进入构建阶段，现在不能更改。因此，没有更多的元素可以添加到流中。

以下是说明 add()方法的示例:

**例 1:**

```
// Java code to show the implementation
// of LongStream.Builder add(long t)

import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        LongStream.Builder b = LongStream.builder();

        // Inserting elements into the stream
        // using LongStream.Builder add(long t)
        b.add(4L);
        b.add(5L);
        b.add(6L);
        b.add(7L);

        // Creating the Stream
        // The stream has now entered the built phase
        // printing the elements
        System.out.println("Stream successfully built");
        b.build().forEach(System.out::println);
    }
}
```

**Output:**

```
Stream successfully built
4
5
6
7

```

**示例 2:** 说明 IllegalStateException

```
// Java code to show the implementation
// of LongStream.Builder add(T t)

import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        LongStream.Builder b = LongStream.builder();

        // using LongStream.Builder add(T t)
        b.add(4L);
        b.add(5L);
        b.add(6L);
        b.add(7L);

        // Creating the Stream
        // The stream has now entered the built phase
        // printing the elements
        System.out.println("Stream successfully built");
        b.build().forEach(System.out::println);

        // Trying to add another element into the stream
        // Since the Stream is in built phase
        // This operation is not possible now
        // Hence add() will throw exception now

        try {
            b.add(50L);
        }
        catch (Exception e) {
            System.out.println("Exception thrown "
                               + "when now adding element into the stream: "
                               + e);
        }
    }
}
```

**Output:**

```
Stream successfully built
4
5
6
7
Exception thrown when now adding element into the stream: java.lang.IllegalStateException

```