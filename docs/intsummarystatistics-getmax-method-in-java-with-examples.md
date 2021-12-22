# Java 中的 IntSummaryStatistics getMax()方法，带示例

> 原文:[https://www . geesforgeks . org/intsummarystatics-getmax-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intsummarystatistics-getmax-method-in-java-with-examples/)

Java 中 **[IntSummaryStatistics 类的 **getMax()** 方法用于获取该 IntSummaryStatistics 中的最大记录数。](https://www.geeksforgeeks.org/java-util-intsummarystatistics-class-with-examples/)**

**语法:**

```java
public int getMax()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**该方法返回 IntSummaryStatistics 中记录的最大值。

**程序:**

```java
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

        System.out.println("The maximum of values is "
                           + intSummaryStatistics.getMax());
    }
}
```

**输出:**

```java
The maximum of values is 50

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/intsummarystatistics . html # getMax()](https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html#getMax())