# 用 Java 装箱的双流()，示例

> 原文:[https://www . geesforgeks . org/double stream-box-Java-examples/](https://www.geeksforgeeks.org/doublestream-boxed-java-examples/)

**Double Stream box()**返回一个由该流的元素组成的流，每个元素都被装箱为一个 Double。

**注意:**双流盒装()是一个 ***的中间操作。*** 这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。
**语法:**

```
Stream<**Double**> boxed()

```

**参数:**

1.  **[流](https://www.geeksforgeeks.org/stream-in-java/) :** 支持顺序和并行聚合操作的元素序列。
2.  **Double:**Double 类在对象中包装一个基元类型 Double 的值。类型为 double 的对象包含类型为 Double 的单个字段。

**返回值:**该函数返回一个被装箱为双精度的流。

**例 1 :**

```
// Java code for DoubleStream boxed()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(3.2, 8.4, 3.6, 4.7);

        // Creating a Stream of Doubles
        // Using DoubleStream boxed() to return
        // a Stream consisting of the elements
        // of this stream, each boxed to a Double.
        Stream<Double> stream1 = stream.boxed();

        // Displaying the elements
        stream1.forEach(System.out::println);
    }
}
```

输出:

```
3.2
8.4
3.6
4.7

```

**例 2 :**

```
// Java code for DoubleStream boxed()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(3.2, 8.4, 3.6, 4.7);

        // Creating a Stream of Doubles
        // Using DoubleStream boxed() to return
        // a Stream consisting of the elements
        // of this stream, each boxed to a Double.
        Stream<Double> stream1 = stream.boxed();

        Stream<Object> stream2 = Stream.concat(stream1,
                                   Stream.of("Geeks", "for", "Geeks"));

        // Displaying the elements
        stream2.forEach(System.out::println);
    }
}
```

输出:

```
3.2
8.4
3.6
4.7
Geeks
for
Geeks

```