# Java 中的 IntSummaryStatistics getCount()方法，带示例

> 原文:[https://www . geesforgeks . org/intsummarystatics-getcount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intsummarystatistics-getcount-method-in-java-with-examples/)

Java 中 **[IntSummaryStatistics 类的 **getCount()** 方法用于获取该 IntSummaryStatistics 中的记录数。](https://www.geeksforgeeks.org/java-util-intsummarystatistics-class-with-examples/)**

**语法:**

```java
public long getCount()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**该方法返回 IntSummaryStatistics 中的记录数。

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

        System.out.println("The count of values is "
                           + intSummaryStatistics.getCount());
    }
}
```

**输出:**

```java
The count of values is 5

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/intsummarystatistics . html # getCount()](https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html#getCount())