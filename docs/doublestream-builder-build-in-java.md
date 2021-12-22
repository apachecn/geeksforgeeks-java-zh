# 双流。Java 中的 Builder build()

> 原文:[https://www . geesforgeks . org/double stream-builder-build-in-Java/](https://www.geeksforgeeks.org/doublestream-builder-build-in-java/)

DoubleStream。构建器构建()构建流，将该构建器转换到*构建状态*。

**语法:**

```java
DoubleStream build()
```

**返回值:**这个方法返回构建的流。

**注意:**一个流构建器有一个生命周期，从*构建阶段*开始，在此期间可以添加元素，然后过渡到*构建阶段*，之后可以不添加元素。构建阶段在调用 build()方法时开始，该方法创建一个有序流，其元素是按照添加顺序添加到流构建器中的元素。

下面是举例说明 build()方法的例子:

**例 1:**

```java
// Java code to show the implementation
// of DoubleStream.Builder build()

import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a Stream in building phase
        DoubleStream.Builder b = DoubleStream.builder();

        // Adding elements into the stream
        b.add(1.2);
        b.add(2.4);
        b.add(3.87);
        b.add(4.78);

        // Constructing the built stream using build()
        // This will enter the stream in built phase
        b.build().forEach(System.out::println);
    }
}
```

**Output:**

```java
1.2
2.4
3.87
4.78

```

**示例 2:** 在调用 build()方法后尝试在中添加元素(当流处于构建阶段时)。

```java
// Java code to show the implementation
// of DoubleStream.Builder build()

import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a Stream in building phase
        DoubleStream.Builder b = DoubleStream.builder();

        // Adding elements into the stream
        b.add(1.2);
        b.add(2.4);
        b.add(3.87);
        b.add(4.78);

        // Constructing the built stream using build()
        // This will enter the stream in built phase
        // Now no more elements can be added to this stream
        b.build().forEach(System.out::println);

        // Trying to add more elements in built phase
        // This will cause exception
        try {
            b.add(50.547);
        }
        catch (Exception e) {
            System.out.println("\nException: " + e);
        }
    }
}
```

**Output:**

```java
1.2
2.4
3.87
4.78

Exception: java.lang.IllegalStateException

```