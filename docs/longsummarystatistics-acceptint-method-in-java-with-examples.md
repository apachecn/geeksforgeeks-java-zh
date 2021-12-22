# Java 中 LongSummaryStatistics accept(int)方法示例

> 原文:[https://www . geesforgeks . org/longsummarystatistics-accept int-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longsummarystatistics-acceptint-method-in-java-with-examples/)

Java 中 **LongSummaryStatistics 类**的 **accept(int)** 方法用于将给定的整数值接受到这个汇总信息中。

**语法:**

```
public void accept(int value)

```

**参数:**该方法接受值作为要记录到该 LongSummaryStatistics 中的参数。

**返回值:**这个方法不返回任何东西。

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

        System.out.println(longSummaryStatistics.toString());
    }
}
```

**输出:**

```
LongSummaryStatistics{count=5, sum=150, min=10, average=30.000000, max=50}

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/longsummarystatistics . html # accept(int)](https://docs.oracle.com/javase/10/docs/api/java/util/LongSummaryStatistics.html#accept(int))