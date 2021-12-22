# Java 8 |收集器计数()带示例

> 原文:[https://www . geesforgeks . org/Java-8-collectors-counting-with-examples/](https://www.geeksforgeeks.org/java-8-collectors-counting-with-examples/)

**Collectors counting()** 方法用于统计流中传递的元素数量作为参数。它返回一个接受 T 类型元素的收集器，该收集器计算输入元素的数量。如果不存在任何元素，则结果为 0。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。它返回流中经过各种流水线流操作(如过滤、缩减等)后到达 collect()方法的元素总数。

**语法:**

```java
public static <T> Collector<T, ?, Long> counting()

```

其中提到的术语如下:

*   **接口收集器< **T、A、R** >** :一种将输入元素累加到一个可变结果容器中的可变约简操作，可选地在所有输入元素都被处理之后将累加的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
    *   **T:** 归约运算的输入元素类型。
    *   **A:** 还原操作的可变累加类型。
    *   **R:** 归约运算的结果类型。
*   **Long:**Long 类在对象中包装一个长的基元类型的值。long 类型的对象包含类型为 Long 的单个字段。此外，此类提供了将 long 转换为 String 和将 String 转换为 long 的几种方法，以及处理 long 时有用的其他常量和方法。
*   **T:** 输入元素的类型。

**参数:**该方法不取任何参数。

**返回值:**对输入元素进行计数的采集器。计数作为龙对象返回。

下面是举例说明计数()方法:

**程序 1:**

```java
// Java code to show the implementation of
// Collectors counting() method

import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream of strings
        Stream<String> s = Stream.of("1", "2", "3", "4");

        // using Collectors counting() method to
        // count the number of input elements
        long ans = s.collect(Collectors.counting());

        // displaying the required count
        System.out.println(ans);
    }
}
```

**Output:**

```java
4

```

**程序 2:** 当没有元素作为输入元素传递时。

```java
// Java code to show the implementation of
// Collectors counting() method

import java.util.stream.Collectors;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream of strings
        Stream<String> s = Stream.of();

        // using Collectors counting() method to
        // count the number of input elements
        long ans = s.collect(Collectors.counting());

        // displaying the required count
        System.out.println(ans);
    }
}
```

**Output:**

```java
0

```