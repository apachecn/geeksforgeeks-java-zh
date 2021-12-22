# Java 中的 DoubleSummaryStatistics getMin()方法，示例

> 原文:[https://www . geesforgeks . org/double summary statistics-getmin-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublesummarystatistics-getmin-method-in-java-with-examples/)

Java 中 **DoubleSummaryStatistics 类的 **getMin()** 方法用来获取这个 DoubleSummaryStatistics 中最少的记录。**

**语法:**

```java
public double getMin()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**该方法返回该 DoubleSummaryStatistics 中记录的最小值。

**程序:**

```java
// Java program to demonstrate
// the above method

import java.util.*;

public class DoubleSummaryStatisticsDemo {
    public static void main(String[] args)
    {

        DoubleSummaryStatistics doubleSummaryStatistics
            = new DoubleSummaryStatistics();

        List<Double> list = new LinkedList<>();
        list.add(95.7);
        list.add(234.6767);
        list.add(243.5);
        list.add(50.0);
        list.add(45.6);
        list.add(45664.0);
        list.add(7007.777);
        list.add(5677.0);
        list.add(0.0);
        list.add(45664.7);

        Iterator<Double> iterator = list.listIterator();
        while (iterator.hasNext()) {

            // Add the doubles to the
            // DoubleSummaryStatistics object
            doubleSummaryStatistics
                .accept(iterator.next());
        }

        System.out.println(doubleSummaryStatistics
                               .toString());

        System.out.println("The minimum of values is "
                           + doubleSummaryStatistics
                                 .getMin());
    }
}
```

**Output:**

> double summary statistics { count = 10，sum=104682.953700，min=0.000000，average=10468.295370，max=45664.700000}
> 最小值为 0.0

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/double summary statistics . html # getMin()](https://docs.oracle.com/javase/10/docs/api/java/util/DoubleSummaryStatistics.html#getMin())