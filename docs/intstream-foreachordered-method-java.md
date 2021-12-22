# Java 中的 IntStream forEachOrdered()方法

> 原文:[https://www . geesforgeks . org/int stream-foreachordered-method-Java/](https://www.geeksforgeeks.org/intstream-foreachordered-method-java/)

**IntStream forEachOrdered(IntConsumer action)**按照相遇顺序为该流的每个元素执行一个操作。IntStream forEachOrdered(IntConsumer action)是一种 ***终端操作*** ，即它可能会遍历流以产生结果或副作用。

**语法:**

```java
void forEachOrdered(IntConsumer action)

```

**参数:** IntConsumer 表示接受单个 int 值参数且不返回结果的操作。这是消费者对 int 的原始类型专门化。

**注意:**forEachOrdered(IntConsumer action)对该流的每个元素执行一个操作，如果该流具有定义的遭遇顺序，则在该流的 ***遭遇顺序*** 中执行。

**例 1 :**

```java
// Java code for IntStream forEachOrdered
// (IntConsumer action) in Java 8
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 3, 4, 5);

        // Using IntStream.forEachOrdered
        stream.forEachOrdered(System.out::println);
    }
}
```

**Output:**

```java
2
3
4
5

```

**例 2 :**

```java
// Java code for IntStream forEachOrdered
// (IntConsumer action) in Java 8
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(5, 11);

        // Using IntStream.forEachOrdered() on
        // sequential stream
        stream.forEachOrdered(System.out::println);
    }
}
```

**Output:**

```java
5
6
7
8
9
10

```

**例 3 :**

```java
// Java code for IntStream forEachOrdered
// (IntConsumer action) in Java 8
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(5, 11);

        // Using IntStream.forEachOrdered() on
        // parallel stream
        stream.parallel().forEachOrdered(System.out::println);
    }
}
```

输出:

```java
5
6
7
8
9
10

```