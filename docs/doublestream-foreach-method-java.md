# Java 中的 DoubleStream forEach()方法

> 原文:[https://www . geesforgeks . org/double stream-foreach-method-Java/](https://www.geeksforgeeks.org/doublestream-foreach-method-java/)

**双流 forEach(双消费者动作)**为流的每个元素执行一个动作。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。

**语法:**

```java
void forEach(DoubleConsumer action)

```

**参数:**

1.  **DoubleConsumer :** 表示接受单个双值参数且不返回结果的操作。这是双消费的原始类型专业化。

**注意:**这个操作的行为是明确的**不确定的**。此外，对于任何给定的元素，动作可以在库选择的任何时间和任何线程中执行。

**例 1 :**

```java
// Java code for DoubleStream forEach
// (DoubleConsumer action) in Java 8
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(7.3, 8.2, 9.5, 10.6);

        // Using DoubleStream.forEach
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```java
7.3
8.2
9.5
10.6

```

**注意:**对于并行流，double stream forEach(double consumer action)不保证尊重流的相遇顺序，因为这样做会牺牲并行的好处。下面是例子。

**例 2 :**

```java
// Java code for DoubleStream forEach
// (DoubleConsumer action) in Java 8
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(7.3, 8.2, 9.5, 10.6);

        // Using DoubleStream.forEach() on parallel stream
        stream.parallel().forEach(System.out::println);
    }
}
```

**Output:**

```java
9.5
7.3
8.2
10.6

```