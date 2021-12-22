# Java |收集器平均长(ToLongFunction mapper)示例

> 原文:[https://www . geesforgeks . org/Java-collectors-averaging long-to long function-mapper-with-examples/](https://www.geeksforgeeks.org/java-collectors-averaginglong-tolongfunction-mapper-with-examples/)

**收藏者平均长(ToLongFunction <？super T > mapper)** 方法用于查找参数中传递的长值的平均值。此方法返回一个收集器，该收集器生成应用于输入元素的长值函数的算术平均值。如果没有元素作为输入元素传递，则此方法返回 0。

该方法计算[算术平均值](https://www.geeksforgeeks.org/progressions-ap-gp-hp-and-practice-problems/)的公式为:

<center>![  {\displaystyle A={\frac {1}{n}}\sum _{i=1}^{n}a_{i}={\frac {a_{1}+a_{2}+\cdots +a_{n}}{n}}}  ](img/e365b32e748913eb82cc5b6423b274fd.png "Rendered by QuickLaTeX.com")</center>

**语法:**

```java
public static <T> 
    Collector<T, ?, Double> 
        averagingLong(ToLongFunction<? super T> mapper)

```

其中术语如下:

*   **接口收集器< T，A，R >** :一种可变的约简操作，将输入元素累积到一个可变的结果容器中，在处理完所有输入元素后，可选地将累积的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
    *   **T:** 归约运算的输入元素类型。
    *   **A:** 还原操作的可变累加类型。
    *   **R:** 归约运算的结果类型。
*   **Double:**Double 类在对象中包装一个基元类型 Double 的值。类型为 double 的对象包含类型为 Double 的单个字段。
*   **ToLongFunction :** 表示产生长值结果的函数。

**参数:**该方法接受一个参数**映射器**，该参数是使用 TolongFunctions 转换为 Long 的长值流。 *ToLongFunction* 是一个函数，它在流的对象上提取一个长类型的值。

以下是说明 averagingLong()方法的示例:

**程序 1:**

```java
// Java code to show the implementation of
// averagingLong(ToLongFunction mapper) function

import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a string stream
        Stream<String> s = Stream.of("3", "4", "5");

        // using Collectors averagingLong(ToLongFunction mapper)
        // method to find arithmetic mean of inputs given
        double ans = s
                         .collect(Collectors
                                      .averagingLong(
                                          num -> Long.parseLong(num)));

        // displaying the result
        System.out.println(ans);
    }
}
```

**Output:**

```java
4.0

```

**程序 2:**

```java
// Java code to show the implementation of
// averagingLong(ToLongFunction mapper) function

import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a string stream
        Stream<String> s = Stream.of("7", "8", "9", "10");

        // using Collectors averagingLong(ToLongFunction mapper)
        // method to find arithmetic mean of inputs given
        double ans = s
                         .collect(Collectors
                                      .averagingLong(
                                          num -> Long.parseLong(num)));

        // displaying the result
        System.out.println(ans);
    }
}
```

**Output:**

```java
8.5

```

**程序 3:** 当没有值作为参数传递时。

```java
// Java code to show the implementation of
// averagingLong(ToLongFunction mapper) function

import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a string stream
        Stream<String> s = Stream.of();

        // using Collectors averagingLong(ToLongFunction mapper)
        // method to find arithmetic mean of inputs given
        double ans = s
                         .collect(Collectors
                                      .averagingLong(
                                          num -> Long.parseLong(num)));

        // displaying the result
        System.out.println(ans);
    }
}
```

**Output:**

```java
0.0

```