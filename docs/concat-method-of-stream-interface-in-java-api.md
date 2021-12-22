# 在 Java API 中串联()流接口的方法

> 原文:[https://www . geesforgeks . org/concat-流方法-java 中的接口-api/](https://www.geeksforgeeks.org/concat-method-of-stream-interface-in-java-api/)

[Java API 中的流接口](https://www.geeksforgeeks.org/stream-in-java/)在 Java 中是存在的。Util.Stream 和正在扩展的 BaseStream < T、Stream<T>T5 界面。这个接口是在任何对象流上创建的，它提供了许多可以用来修改这些对象流的方法。

**concat()方法:**

该方法的名称表明，该方法主要用于将两个流连接在一起。在串联中，第一个流的内容后面是第二个流。最终输出流可以是有序的或并行的。这主要取决于输入流。这里需要注意的要点是，当这个连接流关闭时，两个连接流也关闭。

由于一次只能连接两个流，因此可以使用以下思想连接几个流:首先，我们连接两个流，然后将该结果与另一个流连接，以便最后连接所有流。

**例:**

> 让 s1 =溪流 1
> 
> S2 =溪流 2
> 
> 。
> 
> 。
> 
> 。
> 
> sn =流 n
> 
> 所以所有流的串联可以表示为:
> 
> 结果流为= concat(s1，concat(s2，concat(…………)。))
> 
> 因此产生的流具有顺序为 S1 S2 3s 4 S5 s 6…sn 的所有流。
> 
> T21】

该方法的声明语法如下所示。

> 静态< T >流< T >串联(流<？延伸 T > A，流<？延伸 T > B)。
> 
> 这里我们有两个类型为 T 的流，即 A 和 b。这里要注意的主要事情是这个方法是一个静态方法。

下面是问题陈述的实现:

**例 1:**

## Java

```
// Implementation of concat() method
// of Stream interface in Java API

import java.util.*;

// importing the necessary classes to
// implement the stream interface
import java.util.stream.Stream;

// save as file named GFG2.java
public class GFG2 {

    // main method
    public static void main(String[] args) throws Exception
    {

        // first stream
        Stream<Integer> s1 = Stream.of(1, 2, 3, 4);

        // second stream
        Stream<Integer> s2 = Stream.of(5, 6, 7, 8);

        // concatenation and printing
        // of the stream elements.
        Stream.concat(s1, s2).distinct().forEach(
            ele -> System.out.println(ele));
    }
}
```

**输出**

```
1
2
3
4
5
6
7
8
```

**例 2:**

## **Java**

```
// Implementation of concat() method
// of Stream interface in Java API
import java.util.*;

import java.util.stream.DoubleStream;

// importing the necessary classes
// to implement the stream interface
import java.util.stream.Stream;

// save as file named GFG2.java
public class GFG2 {

    // main method
    public static void main(String[] args) throws Exception
    {

        // first stream
        DoubleStream s1
            = DoubleStream.of(1.025, 2.0687, 3.01);

        // second stream
        DoubleStream s2 = DoubleStream.of(5.2587410, 8);

        // concatenation and printing
        // of the stream elements.
        DoubleStream.concat(s1, s2).distinct().forEach(
            ele -> System.out.println(ele));
    }
}
```

****输出**

```
1.025
2.0687
3.01
5.258741
8.0
```** 

**同样，我们可以有不同类型的流，比如字符串流、字符流等等。**