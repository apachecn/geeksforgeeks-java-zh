# Java 中的 IntSummaryStatistics getSum()方法，带示例

> 原文:[https://www . geesforgeks . org/intsummarystatics-getsum-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intsummarystatistics-getsum-method-in-java-with-examples/)

Java 中 **IntSummaryStatistics 类的 **getSum()** 方法用来获取这个 IntSummaryStatistics 中记录的总和。**

**语法:**

```
public long getSum()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**该方法返回 IntSummaryStatistics 中记录的总和。

**程序:**

```
// Java program to demonstrate
// the above method

import java.util.*;

public class IntSummaryStatisticsDemo {
    public static void main(String[] args)
    {

        IntSummaryStatistics intSummaryStatistics
            = new IntSummaryStatistics();

        List<Integer> list
            = Arrays.asList(10, 20, 30, 40, 50);

        Iterator<Integer> iterator = list.listIterator();
        while (iterator.hasNext()) {

            // Add the integers to the IntSummaryStatistics object
            intSummaryStatistics.accept(iterator.next());
        }

        System.out.println("The sum of values is "
                           + intSummaryStatistics.getSum());
    }
}
```

**输出:**

```
The sum of values is 150

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/intsummarystatistics . html # getSum()](https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html#getSum())