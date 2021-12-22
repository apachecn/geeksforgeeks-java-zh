# Java 中的 LongSummaryStatistics getMin()方法，带示例

> 原文:[https://www . geesforgeks . org/longsummarystatistics-getmin-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longsummarystatistics-getmin-method-in-java-with-examples/)

Java 中 **LongSummaryStatistics 类**的 **getMin()** 方法用来获取这个 LongSummaryStatistics 中记录的最小值。

**语法:**

```
public int getMin()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**这个方法返回这个 LongSummaryStatistics 中记录的最小值。

**程序:**

```
// Java program to demonstrate
// the above method

import java.util.*;

public class LongSummaryStatisticsDemo {
    public static void main(String[] args)
    {

        LongSummaryStatistics longSummaryStatistics
            = new LongSummaryStatistics();

        List<Integer> list
            = Arrays.asList(10, 20, 30, 40, 50);

        Iterator<Integer> iterator = list.listIterator();
        while (iterator.hasNext()) {

            // Add the integers to the LongSummaryStatistics object
            longSummaryStatistics.accept(iterator.next());
        }

        System.out.println("The minimum of values is "
                           + longSummaryStatistics.getMin());
    }
}
```

**输出:**

```
The minimum of values is 10

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/longsummarystatistics . html # getMin()](https://docs.oracle.com/javase/10/docs/api/java/util/LongSummaryStatistics.html#getMin())