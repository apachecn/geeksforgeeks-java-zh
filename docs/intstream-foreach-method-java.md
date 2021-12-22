# Java 中的 IntStream forEach()方法

> 原文:[https://www . geesforgeks . org/int stream-foreach-method-Java/](https://www.geeksforgeeks.org/intstream-foreach-method-java/)

**IntStream forEach(IntConsumer action)**为流的每个元素执行一个操作。IntStream forEach(IntConsumer action)是一个 ***终端操作*** ，也就是说，它可能会遍历该流以产生结果或副作用。

**语法:**

```
void forEach(IntConsumer action)

```

**参数:** IntConsumer 表示接受单个 int 值参数且不返回结果的操作。这是消费者对 int 的原始类型专门化。

**注意:**这个操作的行为是明确的**不确定的**。此外，对于任何给定的元素，动作可以在库选择的任何时间和任何线程中执行。

**例 1 :**

```
// Java code for IntStream forEach
// (IntConsumer action) in Java 8
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(7, 8, 9, 10);

        // Using IntStream.forEach
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```
7
8
9
10

```

**例 2 :**

```
// Java code for IntStream forEach
// (IntConsumer action) in Java 8
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(4, 9);

        // Using IntStream.forEach() on sequential stream
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```
4
5
6
7
8

```

**注意:**对于并行流，IntStream forEach(IntConsumer action)不保证尊重流的相遇顺序，因为这样做会牺牲并行的好处。下面是例子。

**例 3 :**

```
// Java code for IntStream forEach
// (IntConsumer action) in Java 8
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(4, 9);

        // Using IntStream.forEach() on parallel stream
        stream.parallel().forEach(System.out::println);
    }
}
```

**Output:**

```
6
8
7
5
4

```