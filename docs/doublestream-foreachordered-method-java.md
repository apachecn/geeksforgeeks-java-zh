# Java 中的 DoubleStream forEachOrdered()方法

> 原文:[https://www . geesforgeks . org/double stream-foreachordered-method-Java/](https://www.geeksforgeeks.org/doublestream-foreachordered-method-java/)

**双流 forEachOrdered(双消费者动作)**按照相遇顺序为该流的每个元素执行一个动作。double stream forEachOrdered(double consumer action)是一种 ***终端操作*** ，也就是说，它可能会遍历流以产生结果或副作用。

**语法:**

```java
void forEachOrdered(DoubleConsumer action)

```

**参数:** DoubleConsumer 表示接受单个双值参数且不返回结果的操作。这是双消费的原始类型专业化。

**注意:**forEachOrdered(double consumer action)对该流的每个元素执行一个操作，如果该流具有定义的相遇顺序，则在该流的 ***相遇顺序*** 中执行。

**例 1 :**

```java
// Java code for DoubleStream forEachOrdered
// (DoubleConsumer action) in Java 8
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream =
          DoubleStream.of(2.2, 3.3, 4.4, 5.5);

        // Using DoubleStream.forEachOrdered
        stream.forEachOrdered(System.out::println);
    }
}
```

**Output:**

```java
2.2
3.3
4.4
5.5

```

**例 2 :**

```java
// Java code for DoubleStream forEachOrdered
// (DoubleConsumer action) in Java 8
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = 
              DoubleStream.of(5.3, 6.4, 7.3, 6.1);

        // Using DoubleStream.forEachOrdered() on
        // parallel stream
        stream.parallel().forEachOrdered(System.out::println);
    }
}
```

**Output:**

```java
5.3
6.4
7.3
6.1

```