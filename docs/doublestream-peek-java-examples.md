# Java 中的 DoubleStream peek()，示例

> 原文:[https://www . geesforgeks . org/double stream-peek-Java-examples/](https://www.geeksforgeeks.org/doublestream-peek-java-examples/)

**双流 peek()** 是*T3T5 中的一个方法。该函数返回一个由该流的元素组成的流，并在从结果流中消费元素时对每个元素执行所提供的操作。*

双流 peek()是一个**中间操作**。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```java
DoubleStream peek(DoubleConsumer action) 

```

**参数:**

1.  **双流:**原始双值元素的序列。
2.  **DoubleConsumer :** 表示接受单个双值参数且不返回结果的操作。

**返回值:**函数返回一个并行的双流。

**注意:**这个方法的存在主要是为了支持调试。

**例 1 :** 进行求和运算，求给定双流元素的和。

```java
// Java code for DoubleStream peek()
// where the action performed is to get
// sum of all elements.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a stream of doubles
        DoubleStream stream =
                DoubleStream.of(2.2, 3.3, 4.5, 6.7);

        // performing action sum on elements of
        // given range and storing the result in sum
        double sum = stream.peek(System.out::println).sum();

        // Displaying the result of action performed
        System.out.println("sum is : " + sum);
    }
}
```

**Output:**

```java
2.2
3.3
4.5
6.7
sum is : 16.7

```

**示例 2 :** 对给定双流的元素执行计数操作。

```java
// Java code for DoubleStream peek()
// where the action performed is to get
// count of all elements in given range
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a stream of doubles
        DoubleStream stream =
                  DoubleStream.of(2.2, 3.3, 4.5, 6.7);

        // performing count operation on elements of
        // given DoubleStream and storing the result in Count
        long Count = stream.peek(System.out::println).count();

        // Displaying the result of action performed
        System.out.println("count : " + Count);
    }
}
```

**Output:**

```java
2.2
3.3
4.5
6.7
count : 4

```

**示例 3 :** 对给定双流的元素执行平均运算。

```java
// Java code for DoubleStream peek()
// where the action performed is to get
// average of all elements.
import java.util.*;
import java.util.OptionalDouble;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a stream of doubles
        DoubleStream stream =
                DoubleStream.of(2.2, 3.3, 4.5, 6.7);
        ;

        // performing action "average" on elements of
        // given DoubleStream and storing the result in avg
        OptionalDouble avg = stream.peek(System.out::println)
                                 .average();

        // If a value is present, isPresent()
        // will return true, else -1 is displayed.
        if (avg.isPresent()) {
            System.out.println("Average is : " + avg.getAsDouble());
        }
        else {
            System.out.println("-1");
        }
    }
}
```

**Output:**

```java
2.2
3.3
4.5
6.7
Average is : 4.175

```