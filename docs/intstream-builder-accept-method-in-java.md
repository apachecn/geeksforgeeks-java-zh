# IntStream。Java 中的 Builder accept()方法

> 原文:[https://www . geesforgeks . org/int stream-builder-accept-method-in-Java/](https://www.geeksforgeeks.org/intstream-builder-accept-method-in-java/)

**IntStream。Builder accept(int t)** 用于在流的构建阶段将元素插入到元素中。它接受正在构建的流的元素。

**语法:**

```
void accept(int t)
```

**参数:**该方法接受一个强制参数 **t** ，它是输入到流中的元素。

**异常:**当构建器已经转换到构建状态时，该方法抛出**非法状态异常**。这意味着该流已经进入构建阶段，现在不能更改。因此**不能再接受更多的元素进入溪流。**

下面是举例说明 accept()方法的例子:

**例 1:**

```
// Java code to show the implementation
// of IntStream.Builder accept(int t)

import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        IntStream.Builder b = IntStream.builder();

        // Inserting elements into the stream
        // using IntStream.Builder accept(int t)
        b.accept(4);
        b.accept(5);
        b.accept(6);
        b.accept(7);

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
// of IntStream.Builder accept(int t)

import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Declaring an empty Stream
        IntStream.Builder b = IntStream.builder();

        // using IntStream.Builder accept(int t)
        b.accept(4);
        b.accept(5);
        b.accept(6);
        b.accept(7);

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
            b.accept(50);
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

```
Stream successfully built
4
5
6
7
Exception thrown when now accepting element into the stream: java.lang.IllegalStateException

```