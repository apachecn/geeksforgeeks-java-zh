# Java 中的 IntStream summaryStatistics()

> 原文:[https://www . geesforgeks . org/int stream-summary statistics-Java/](https://www.geeksforgeeks.org/intstream-summarystatistics-java/)

**IntStream summary statistics()**返回一个 IntSummaryStatistics，描述关于这个流的元素的各种汇总数据，比如 IntStream 中元素数量的计数、IntStream 中所有元素的平均值、IntStream 中元素的最小值和最大值等等。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。

**语法:**

```
IntSummaryStatistics summaryStatistics()

```

**参数:**

1.  **IntSummaryStatistics :** 用于收集统计信息(如计数、最小值、最大值、总和和平均值)的状态对象。

**返回值:**IntSummaryStatistics summaryStatistics()返回一个 IntSummaryStatistics，描述了关于这个流的元素的各种汇总数据。

**注:** IntStream summaryStatistics()是**约简**的特例。约简操作，也称为 ***折叠*** 获取一系列输入元素，并通过重复应用组合操作将它们组合成单个汇总结果。组合运算可以是求一组数的和或最大值。

**示例 1 :** 使用 IntStream summaryStatistics()获取给定 IntStream 中存在的元素的 IntSummaryStatistics。

```
// Java code for IntStream summaryStatistics()
// to get various summary data about the
// elements of the stream.
import java.util.stream.IntStream;
import java.util.IntSummaryStatistics;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(4, 5, 6, 7);

        // Using IntStream summaryStatistics()
        IntSummaryStatistics summary_data = 
                        stream.summaryStatistics();

        // Displaying the various summary data
        // about the elements of the stream
        System.out.println(summary_data);
    }
}
```

输出:

```
IntSummaryStatistics{count=4, sum=22, min=4, average=5.500000, max=7}

```

**示例 2 :** 使用 IntStream summaryStatistics()获取给定范围内存在的元素的 IntSummaryStatistics。

```
// Java code for IntStream summaryStatistics()
// to get various summary data about the
// elements of the stream.
import java.util.stream.IntStream;
import java.util.IntSummaryStatistics;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream of elements
        // in range [5, 9)
        IntStream stream = IntStream.range(5, 9);

        // Using IntStream summaryStatistics()
        IntSummaryStatistics summary_data =
                       stream.summaryStatistics();

        // Displaying the various summary data
        // about the elements of the stream
        System.out.println(summary_data);
    }
}
```

输出:

```
IntSummaryStatistics{count=4, sum=26, min=5, average=6.500000, max=8}

```