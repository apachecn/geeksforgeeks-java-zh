# LongStream。Java 中的 Builder accept()方法

> 原文:[https://www . geesforgeks . org/longstream-builder-accept-method-in-Java/](https://www.geeksforgeeks.org/longstream-builder-accept-method-in-java/)

**LongStream。Builder accept(long t)** 用于在流的构建阶段将元素插入到元素中。它接受正在构建的流的元素。

**语法:**

```java
void accept(long t)
```

**参数:**该方法接受一个强制参数 **t** ，它是输入到流中的元素。

**异常:**当构建器已经转换到构建状态时，该方法抛出**非法状态异常**。这意味着该流已经进入构建阶段，现在不能更改。因此，流中不能接受更多的元素。

下面是举例说明 accept()方法的例子:

**例 1:**

```java
// Java code to show the implementation
// of LongStream.Builder accept(long t)

import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        LongStream.Builder b = LongStream.builder();

        // Inserting elements into the stream
        // using LongStream.Builder accept(long t)
        b.accept(4L);
        b.accept(5L);
        b.accept(6L);
        b.accept(7L);

        // Creating the Stream
        // The stream has now entered the built phase
        // printing the elements
        System.out.println("Stream successfully built");
        b.build().forEach(System.out::println);
    }
}
```

**Output:**

```java
Stream successfully built
4
5
6
7

```

**示例 2:** 说明 IllegalStateException

```java
// Java code to show the implementation
// of LongStream.Builder accept(T t)

import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        LongStream.Builder b = LongStream.builder();

        // using LongStream.Builder accept(T t)
        b.accept(4L);
        b.accept(5L);
        b.accept(6L);
        b.accept(7L);

        // Creating the Stream
        // The stream has now entered the built phase
        // printing the elements
        System.out.println("Stream successfully built");
        b.build().forEach(System.out::println);

        // Trying to accept another element into the stream
        // Since the Stream is in built phase
        // This operation is not possible now
        // Hence accept() will throw exception now

        try {
            b.accept(50L);
        }
        catch (Exception e) {
            System.out.println("Exception thrown "
                               + "when now accepting element into the stream: "
                               + e);
        }
    }
}
```

**Output:**

```java
Stream successfully built
4
5
6
7
Exception thrown when now accepting element into the stream: java.lang.IllegalStateException

```