# Java 中 LongSummaryStatistics toString()方法，带示例

> 原文:[https://www . geesforgeks . org/longsummarystatistics-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/longsummarystatistics-tostring-method-in-java-with-examples/)

Java 中 **LongSummaryStatistics 类的 **toString()** 方法用来获取这个 LongSummaryStatistics 中记录的字符串表示。**

**语法:**

```java
public long toString()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**该方法返回 LongSummaryStatistics 中记录的字符串表示形式。

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

        System.out.println("The String representation of values is "
                           + longSummaryStatistics.toString());
    }
}
```

**输出:**

```java
The String representation of values is LongSummaryStatistics
{count=5, sum=150, min=10, average=30.000000, max=50}

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/longsummarystatistics . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/util/LongSummaryStatistics.html#toString())