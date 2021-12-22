# Java 中的 LongSummaryStatistics getCount()方法，带示例

> 原文:[https://www . geesforgeks . org/longsummarystatistics-getcount-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longsummarystatistics-getcount-method-in-java-with-examples/)

Java 中 **LongSummaryStatistics 类**的 **getCount()** 方法用于获取这个 LongSummaryStatistics 中的记录数。

**语法:**

```java
public long getCount()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**这个方法返回这个 LongSummaryStatistics 中的记录数。

**程序:**

```java
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

        System.out.println("The count of values is "
                           + longSummaryStatistics.getCount());
    }
}
```

**输出:**

```java
The count of values is 5

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/longsummarystatistics . html # getCount()](https://docs.oracle.com/javase/10/docs/api/java/util/LongSummaryStatistics.html#getCount())