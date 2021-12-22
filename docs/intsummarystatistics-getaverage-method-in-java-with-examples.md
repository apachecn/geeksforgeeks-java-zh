# IntSummaryStatistics getAverage()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/intsummarystatistics-getaverage-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intsummarystatistics-getaverage-method-in-java-with-examples/)

Java 中 **IntSummaryStatistics 类的 **getAverage()** 方法用来获取这个 IntSummaryStatistics 中记录的平均值。**

**语法:**

```
public double getAverage()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**该方法返回 IntSummaryStatistics 中记录的平均值。

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

        System.out.println("The average of values is "
                           + intSummaryStatistics.getAverage());
    }
}
```

**输出:**

```
The average of values is 30.0

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/intsummarystatistics . html # getAverage()](https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html#getAverage())