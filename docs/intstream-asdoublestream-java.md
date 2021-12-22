# Java 中的 IntStream asDoubleStream()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/intstream-asdoublestream-Java/

**int stream as double stream()**返回一个由该流的元素组成的 **DoubleStream** ，转换为 double。这是一个 ***的中级操作。*** 在流实例上调用中间操作，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```
DoubleStream asDoubleStream()
Where, DoubleStream is a sequence of 
primitive double-valued element.
Return Value : IntStream asDoubleStream() returns a
DoubleStream consisting of the elements of this stream, 
converted to double.
```

**例 1 :**

```
// Java code for DoubleStream asDoubleStream()
// to return a DoubleStream consisting of
// the elements of this stream
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(3, 5, 9, 12, 14);

        // Using DoubleStream asDoubleStream()
        DoubleStream stream1 = stream.asDoubleStream();

        // Displaying DoubleStream consisting of
        // the elements of this stream
        stream1.forEach(System.out::println);
    }
}
```

输出:

```
3.0
5.0
9.0
12.0
14.0

```

**例 2 :**

```
// Java code for DoubleStream asDoubleStream()
// to return a DoubleStream consisting of
// the elements of this stream
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream and using asDoubleStream()
        DoubleStream stream = IntStream.range(3, 8).asDoubleStream();

        // Displaying DoubleStream consisting of
        // the elements of this stream
        stream.forEach(System.out::println);
    }
}
```

输出:

```
3.0
4.0
5.0
6.0
7.0

```

**例 3 :**

```
// Java code for DoubleStream asDoubleStream()
// to return a DoubleStream consisting of
// the elements of this stream
import java.util.*;
import java.util.stream.IntStream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream and using asDoubleStream()
        // to display the elements of IntStream and
        // DoubleStream together
        DoubleStream stream = IntStream.range(3, 8)
                                  .peek(System.out::println)
                                  .asDoubleStream();

        // Displaying DoubleStream consisting of
        // the elements of this stream
        stream.forEach(System.out::println);
    }
}
```

输出:

```
3
3.0
4
4.0
5
5.0
6
6.0
7
7.0

```