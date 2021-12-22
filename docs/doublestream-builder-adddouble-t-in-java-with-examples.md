# 双流。生成器用 Java 添加(双 t)示例

> 原文:[https://www . geesforgeks . org/double stream-builder-add double-t-in-Java-with-examples/](https://www.geeksforgeeks.org/doublestream-builder-adddouble-t-in-java-with-examples/)

**双流。Builder add(double t)** 用于在 stream 的构建阶段将元素插入到元素中。它向正在构建的流中添加一个元素。

**语法:**

```
default DoubleStream.Builder add(double t)
```

**参数:**该方法接受一个强制参数 **t** ，它是输入到流中的元素。

**异常:**当构建器已经转换到构建状态时，该方法抛出**illegalstatexception:**。这意味着该流已经进入构建阶段，现在不能更改。因此，没有更多的元素可以添加到流中。

以下是说明 add()方法的示例:

**例 1:**

```
// Java code to show the implementation
// of DoubleStream.Builder add(double t)

import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        DoubleStream.Builder b = DoubleStream.builder();

        // Inserting elements into the stream
        // using DoubleStream.Builder add(double t)
        b.add(4.4);
        b.add(5.84);
        b.add(6);
        b.add(7.47);

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
4.4
5.84
6.0
7.47

```

**示例 2:** 说明 IllegalStateException

```
// Java code to show the implementation
// of DoubleStream.Builder add(T t)

import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        DoubleStream.Builder b = DoubleStream.builder();

        // using DoubleStream.Builder add(T t)
        b.add(4.7);
        b.add(5.9);
        b.add(6);
        b.add(7.785);

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
            b.add(50.784);
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
4.7
5.9
6.0
7.785
Exception thrown when now adding element into the stream: java.lang.IllegalStateException

```