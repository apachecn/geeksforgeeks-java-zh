# IntSummaryStatistics 用示例接受 Java 中的()方法

> 原文:[https://www . geesforgeks . org/intsummarystatistics-accept-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intsummarystatistics-accept-method-in-java-with-examples/)

Java 中 **[IntSummaryStatistics 类](https://www.geeksforgeeks.org/java-util-intsummarystatistics-class-with-examples/)** 的 **accept()** 方法用于将给定值接受到该汇总信息中。

**语法:**

```java
public void accept(int value)

```

**参数:**该方法接受值作为要记录到 IntSummaryStatistics 中的参数。

**返回值:**这个方法不返回任何东西。

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

        System.out.println(intSummaryStatistics.toString());
    }
}
```

**输出:**

```java
IntSummaryStatistics{count=5, sum=150, min=10, average=30.000000, max=50}

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/intsummarystatistics . html # accept(int)](https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html#accept(int))