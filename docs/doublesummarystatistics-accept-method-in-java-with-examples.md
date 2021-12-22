# DoubleSummaryStatistics 用示例接受 Java 中的()方法

> 原文:[https://www . geesforgeks . org/double summarystatistics-accept-method-in-Java-with-examples/](https://www.geeksforgeeks.org/doublesummarystatistics-accept-method-in-java-with-examples/)

Java 中 **DoubleSummaryStatistics 类的 **accept()** 方法用于将给定值接受到这个汇总信息中。**

**语法:**

```
public void accept(double value)

```

**参数:**此方法接受值作为要记录到此双摘要统计中的参数。

**返回值:**这个方法不返回任何东西。

**程序:**

```
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

        double value = 34.45;
        System.out.println("Inserting " + value
                           + " using accept() ");

        doubleSummaryStatistics
            .accept(value);

        System.out.println(doubleSummaryStatistics
                               .toString());
    }
}
```

**Output:**

> 使用 accept()
> 插入 34.45 double summarystatistics { count = 11，sum=104717.403700，min=0.000000，average=9519.763973，max=45664.700000}

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/double summarystatistics . html # accept-double-](https://docs.oracle.com/javase/9/docs/api/java/util/DoubleSummaryStatistics.html#accept-double-)