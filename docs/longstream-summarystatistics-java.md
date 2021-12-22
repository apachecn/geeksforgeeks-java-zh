# Java 中的 LongStream summaryStatistics()

> 原文:[https://www . geesforgeks . org/longstream-summary statistics-Java/](https://www.geeksforgeeks.org/longstream-summarystatistics-java/)

**LongStream summaryStatistics()**返回一个 LongSummaryStatistics，描述关于这个流的元素的各种汇总数据，比如 LongStream 中的元素数量计数、LongStream 中所有元素的平均值、LongStream 中的最小和最大元素等等。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。

**语法:**

```java
LongSummaryStatistics summaryStatistics()

```

**参数:**

1.  **LongSummaryStatistics :** 收集计数、最小值、最大值、总和和平均值等统计信息的状态对象。

**返回值:**LongSummaryStatistics summaryStatistics()返回一个 LongSummaryStatistics，描述关于这个流的元素的各种汇总数据。

**注:** LongStream summaryStatistics()是**约简**的特例。约简操作，也称为 ***折叠*** 获取一系列输入元素，并通过重复应用组合操作将它们组合成单个汇总结果。组合运算可以是求一组数的和或最大值。

**示例 1 :** 使用 LongStream summaryStatistics()获取给定 LongStream 中存在的元素的 LongSummaryStatistics。

```java
// Java code for LongStream summaryStatistics()
// to get various summary data about the
// elements of the stream.
import java.util.stream.LongStream;
import java.util.LongSummaryStatistics;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(4L, 5L, 6L, 7L);

        // Using LongStream summaryStatistics()
        LongSummaryStatistics summary_data =
                                  stream.summaryStatistics();

        // Displaying the various summary data
        // about the elements of the stream
        System.out.println(summary_data);
    }
}
```

输出:

```java
LongSummaryStatistics{count=4, sum=22, min=4, average=5.500000, max=7}

```

**示例 2 :** 使用 LongStream summaryStatistics()获取给定范围内存在的元素的 LongSummaryStatistics。

```java
// Java code for LongStream summaryStatistics()
// to get various summary data about the
// elements of the stream.
import java.util.stream.LongStream;
import java.util.LongSummaryStatistics;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream of elements
        // in range [5, 9)
        LongStream stream = LongStream.range(5L, 9L);

        // Using LongStream summaryStatistics()
        LongSummaryStatistics summary_data = 
                         stream.summaryStatistics();

        // Displaying the various summary data
        // about the elements of the stream
        System.out.println(summary_data);
    }
}
```

输出:

```java
LongSummaryStatistics{count=4, sum=26, min=5, average=6.500000, max=8

```