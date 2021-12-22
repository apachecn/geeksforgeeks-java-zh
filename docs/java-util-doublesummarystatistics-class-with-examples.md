# Java . util . double summary 统计类，带示例

> 原文:[https://www . geesforgeks . org/Java-util-double summary statistics-class-with-examples/](https://www.geeksforgeeks.org/java-util-doublesummarystatistics-class-with-examples/)

**双概要统计**类存在于 **[java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)** 中。它收集了一组[双](https://www.geeksforgeeks.org/java-lang-double-class-java/)对象，在我们处理大量精确实数的情况下非常有用。它维护已处理的值的数量、它们的总和以及各种其他统计信息的计数。该类也可以与 [Streams](https://www.geeksforgeeks.org/stream-in-java/) 一起使用。

它是有用的，因为它保持一个连续的总和、平均值等。因此可以用于统计数据的处理。

**等级体系**

```
java.lang.Object
↳ java.util.DoubleSummaryStatistics

```

**施工人员:**

1.  **DoubleSummaryStatistics()**: A default constructor which initializes the count and sum to zero, and sets max to [Double.NEGATIVE_INFINITY](https://www.geeksforgeeks.org/java-lang-double-class-java/) and min to [Double.POSITIVE_INFINITY](https://www.geeksforgeeks.org/java-lang-double-class-java/).

    **语法:**

    ```
    public DoubleSummaryStatistics()

    ```

**方法**:

1.  **accept()**: nThis function adds the passed double into the statistical data.

    **语法:**

    ```
    public void accept(double value)

    ```

2.  **combine()**: This function combines the statistical data of the passed DoubleSummaryStatistics object with the current statistical data.

    **语法:**

    ```
    public void combine(DoubleSummaryStatistics other)

    ```

3.  **getCount()** :这个方法返回处理的双打次数的计数。

**语法:**

```
public final long getCount()

```

8.  **getSum()**: This method returns the sum of all the doubles processed.

    **语法:**

    ```
    public final long getSum()

    ```

9.  **getAverage()**: This method returns the average of all the doubles processed.

    **语法:**

    ```
    public final double getAverage()

    ```

10.  **getMin()**: This method returns the minimum double of all the doubles processed.

    **语法:**

    ```
    public final double getMin()

    ```

11.  **getMax()**: This method returns the maximum double of all the doubles processed.

    **语法:**

    ```
    public final double getMax()

    ```

12.  **toString()**: This method returns the string representation of all the statistical data contained in the object.

    **语法:**

    ```
    public String toString()

    ```

    **示例**演示双重概要统计的实际应用。

    ```
    // Java program to demonstrate
    // DoubleSummaryStatistics class

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

            // Use various methods to obtain the data
            System.out.println("The count of values is "
                               + doubleSummaryStatistics
                                     .getCount());
            System.out.println("The average of values is "
                               + doubleSummaryStatistics
                                     .getAverage());
            System.out.println("The sum of values is "
                               + doubleSummaryStatistics
                                     .getSum());
            System.out.println("The maximum of values is "
                               + doubleSummaryStatistics
                                     .getMax());
            System.out.println("The minimum of values is "
                               + doubleSummaryStatistics
                                     .getMin());
            System.out.println("The string representation is");
            System.out.println(doubleSummaryStatistics
                                   .toString());
        }
    }
    ```

    **Output:**

    ```
    The count of values is 10
    The average of values is 10468.29537
    The sum of values is 104682.9537
    The maximum of values is 45664.7
    The minimum of values is 0.0
    The string representation is
    DoubleSummaryStatistics{count=10, sum=104682.953700, min=0.000000, average=10468.295370, max=45664.700000}

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/double summarystatistics . html](https://docs.oracle.com/javase/8/docs/api/java/util/DoubleSummaryStatistics.html)