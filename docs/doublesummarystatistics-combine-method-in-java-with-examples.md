# double summary 统计将 Java 中的()方法与示例结合起来

> 原文:[https://www . geesforgeks . org/double summarystatistics-将 java 中的方法与示例结合/](https://www.geeksforgeeks.org/doublesummarystatistics-combine-method-in-java-with-examples/)

Java 中**双概要统计类**的 **combine()** 方法用于将给定的其他双概要统计组合到这个双概要统计中。

**语法:**

```java
public void combine(DoubleSummaryStatistics 
                otherDoubleSummaryStatistics)

```

**参数:**此方法接受**其他双汇总统计**作为要合并到此双汇总统计中的参数。

**返回值:**这个方法不返回任何东西。

**异常:**如果 otherDoubleSummaryStatistics 为空，该方法抛出 **[空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/)** 。

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

        Iterator<Double> iterator = list.listIterator();
        while (iterator.hasNext()) {

            // Add the doubles to the
            // DoubleSummaryStatistics object
            doubleSummaryStatistics
                .accept(iterator.next());
        }

        System.out.println("First DdoubleSummaryStatistics: "
                           + doubleSummaryStatistics
                                 .toString());

        DoubleSummaryStatistics otherDoubleSummaryStatistics
            = new DoubleSummaryStatistics();

        List<Double> list1 = new LinkedList<>();
        list1.add(45664.0);
        list1.add(7007.777);
        list1.add(5677.0);
        list1.add(0.0);
        list1.add(45664.7);

        Iterator<Double> iterator1 = list1.listIterator();
        while (iterator1.hasNext()) {

            // Add the doubles to the
            // DoubleSummaryStatistics object
            otherDoubleSummaryStatistics
                .accept(iterator1.next());
        }

        System.out.println("Second DdoubleSummaryStatistics: "
                           + otherDoubleSummaryStatistics
                                 .toString());

        System.out.println("Combining both DdoubleSummaryStatistics"
                           + " using combine() ");
        doubleSummaryStatistics.combine(otherDoubleSummaryStatistics);

        System.out.println("Combined DdoubleSummaryStatistics: "
                           + doubleSummaryStatistics.toString());
    }
}
```

**Output:**

> 第一个 dddoublesummarystatistics:
> DoubleSummaryStatistics { count = 5，sum=669.476700，min=45.600000，average=133.895340，max=243.500000}
> 第二个 dddoublesummarystatistics:
> DoubleSummaryStatistics { count = 5，sum=104013.477000，min = 0.000000，average = 20000
> 
> 使用 combine()合并两个 DdoubleSummaryStatistics
> 
> 组合 dddoublesummarystatistics:
> DoubleSummaryStatistics { count = 10，sum=104682.953700，min=0.000000，average=10468.295370，max=45664.700000}

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/double summarystatistics . html # combine-Java . util . double summarystatistics-](https://docs.oracle.com/javase/9/docs/api/java/util/DoubleSummaryStatistics.html#combine-java.util.DoubleSummaryStatistics-)