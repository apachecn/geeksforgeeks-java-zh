# Java 中的 IntSummaryStatistics getMin()方法，带示例

> 原文:[https://www . geesforgeks . org/intsummarystatics-getmin-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intsummarystatistics-getmin-method-in-java-with-examples/)

Java 中 **[IntSummaryStatistics 类的 **getMin()** 方法用于获取该 IntSummaryStatistics 中的最少记录。](https://www.geeksforgeeks.org/java-util-intsummarystatistics-class-with-examples/)**

**语法:**

```
public int getMin()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**该方法返回 IntSummaryStatistics 中记录的最小值。

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

        System.out.println("The minimum of values is "
                           + intSummaryStatistics.getMin());
    }
}
```

**输出:**

```
The minimum of values is 10

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/intsummarystatistics . html # getMin()](https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html#getMin())