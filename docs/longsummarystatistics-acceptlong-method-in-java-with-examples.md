# LongSummaryStatistics 用示例接受 Java 中的(长)方法

> 原文:[https://www . geesforgeks . org/longsummarystatistics-accept long-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longsummarystatistics-acceptlong-method-in-java-with-examples/)

Java 中 **LongSummaryStatistics 类**的 **accept(long)** 方法用于将给定的 long 值接受到这个摘要信息中。

**语法:**

```java
public void accept(long value)

```

**参数:**该方法接受值作为要记录到该 LongSummaryStatistics 中的参数。

**返回值:**这个方法不返回任何东西。

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

        long value = 456654;
        longSummaryStatistics.accept(value);

        System.out.println(longSummaryStatistics.toString());
    }
}
```

**输出:**

```java
LongSummaryStatistics{count=6, sum=456804, min=10, average=76134.000000, max=456654}

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/longsummarystatistics . html # accept(long)](https://docs.oracle.com/javase/10/docs/api/java/util/LongSummaryStatistics.html#accept(long))