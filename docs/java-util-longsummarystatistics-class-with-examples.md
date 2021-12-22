# 带有示例的 Java . util . longsummarystatistics 类

> 原文:[https://www . geesforgeks . org/Java-util-longsummarystatistics-class-with-examples/](https://www.geeksforgeeks.org/java-util-longsummarystatistics-class-with-examples/)

**LongSummaryStatistics** 类存在于 **[java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)** 中。它收集了 Long 对象，在我们处理大整数流的情况下非常有用。它维护已处理的值的数量、它们的总和以及各种其他统计信息的计数。该类也可以与 **[Streams](https://www.geeksforgeeks.org/stream-in-java/)** 一起使用。

它是有用的，因为它保持一个连续的总和、平均值等。因此可以用于统计数据的处理。

**等级体系**

```java
java.lang.Object
↳ java.util.LongSummaryStatistics

```

**施工人员**

1.  **LongSummaryStatistics()** :默认构造函数，将计数和求和初始化为零，将 max 设置为 **Long。MIN_VALUE** 和 MIN 至**长。最大值**。

    ```java
    public LongSummaryStatistics()

    ```

**方法:**

1.  **accept()** :函数重载，将传递的整数或长值加入统计数据。

    ```java
    public void accept(int value)
    public void accept(long value)

    ```

2.  **combine()** :该函数将传递的 LongSummaryStatistics 对象的统计数据与当前统计数据进行合并。

    ```java
    public void combine(LongSummaryStatistics other)

    ```

3.  **getCount()** :返回已处理的长值数的计数。

    ```java
    public final long getCount()

    ```

4.  **getSum()** :返回所有已处理长值的总和。

    ```java
    public final long getSum()

    ```

5.  **getAverage()** :返回所有已处理长值的平均值。

    ```java
    public final double getAverage()

    ```

6.  **getMin()** :返回所有已处理长值的最小整数。

    ```java
    public final long getMin()

    ```

7.  **getMax()** :返回所有已处理长值的最大整数。

    ```java
    public final long getMax()

    ```

8.  **toString()**: Returns the string representation of all the statistical data contained in the object.

    ```java
    public String toString()

    ```

    **示例**演示 LongSummaryStatistics 在运行。

    ```java
    // Java program to demonstrate
    // LongSummaryStatistics class

    import java.util.*;

    public class LongSummaryStatisticsDemo {
        public static void main(String[] args)
        {
            LongSummaryStatistics longSummaryStatistics
                = new LongSummaryStatistics();
            List<Long> list = new LinkedList<>();
            list.add(100l);
            list.add(200l);
            list.add(300l);
            list.add(400l);
            list.add(500l);
            list.add(600l);
            list.add(700l);
            list.add(800l);
            list.add(900l);
            list.add(1000l);

            Iterator<Long> iterator = list.listIterator();
            while (iterator.hasNext()) {
                // Add the values to the LongSummaryStatistics object
                longSummaryStatistics.accept(iterator.next());
            }

            // Use various methods to obtain the data
            System.out.println("The count of values is "
                               + longSummaryStatistics.getCount());
            System.out.println("The average of values is "
                               + longSummaryStatistics.getAverage());
            System.out.println("The sum of values is "
                               + longSummaryStatistics.getSum());
            System.out.println("The maximum of values is "
                               + longSummaryStatistics.getMax());
            System.out.println("The minimum of values is "
                               + longSummaryStatistics.getMin());
            System.out.println("The string representation is ");
            System.out.println(longSummaryStatistics.toString());
        }
    }
    ```

    **Output:**

    ```java
    The count of values is 10
    The average of values is 550.0
    The sum of values is 5500
    The maximum of values is 1000
    The minimum of values is 100
    The string representation is 
    LongSummaryStatistics{count=10, sum=5500, min=100, average=550.000000, max=1000}

    ```

    **参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/util/longsummarystatistics . html](https://docs.oracle.com/javase/9/docs/api/java/util/LongSummaryStatistics.html)