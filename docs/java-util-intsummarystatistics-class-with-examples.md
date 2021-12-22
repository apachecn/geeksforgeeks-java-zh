# Java . util . intsummarystatistics 类，带示例

> 原文:[https://www . geesforgeks . org/Java-util-intsummarystatics-class-with-examples/](https://www.geeksforgeeks.org/java-util-intsummarystatistics-class-with-examples/)

**IntSummaryStatistics** 类存在于 **[java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)** 中。它收集了[整数](https://www.geeksforgeeks.org/java-lang-integer-class-java/)对象，在我们处理整数流的情况下非常有用。它维护它已经处理的整数的计数、它们的总和以及各种其他统计数据。该类也可以与 **Streams** 一起使用。

它是有用的，因为它保持一个连续的总和、平均值等。因此可以用于统计数据的处理。

**等级体系**

```
java.lang.Object
↳ java.util.IntSummaryStatistics

```

**施工人员**

1.  **IntSummaryStatistics()**: A default constructor which initializes the count and sum to zero, and sets max to **Integer.MIN_VALUE** and min to **Integer.MAX_VALUE**.

    **语法:**

    ```
    public IntSummaryStatistics()

    ```

2.  **IntSummaryStatistics(count, min, max, sum)**: Initializes the various data members with the parameters passed during invocation.

    **语法:**

    ```
    public IntSummaryStatistics(long count, int min, int max, long sum)
                         throws IllegalArgumentException

    ```

**方法**:

1.  **accept()** – This function adds the passed integer into the statistical data.

    **语法:**

    ```
    public void accept(int value)

    ```

2.  **combine()** :此功能将传递的 IntSummaryStatistics 对象的统计数据与当前统计数据进行合并。

**语法:**

```
public void combine(IntSummaryStatistics other)

```

7.  **getCount()**: This method returns the count of the number of integers processed.

    **语法:**

    ```
    public final long getCount()

    ```

8.  **getSum()**: This method returns the sum of all the integers processed.

    **语法:**

    ```
    public final long getSum()

    ```

9.  **getAverage()**: This method returns the average of all the integers processed.

    **语法:**

    ```
    public final double getAverage()

    ```

10.  **getMin()**: This method returns the minimum integer of all the integers processed.

    **语法:**

    ```
    public final int getMin()

    ```

11.  **getMax()**: This method returns the maximum integer of all the integers processed.

    **语法:**

    ```
    public final int getMax()

    ```

12.  **toString()**: This method returns the string representation of all the statistical data contained in the object.

    **语法:**

    ```
    public String toString()

    ```

    **示例**演示 IntSummaryStatistics 的实际应用。

    ```
    // Java program to demonstrate
    // IntSummaryStatistics class

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

            // Use various methods to obtain the data
            System.out.println("The count of values is "
                               + intSummaryStatistics.getCount());
            System.out.println("The average of values is "
                               + intSummaryStatistics.getAverage());
            System.out.println("The sum of values is "
                               + intSummaryStatistics.getSum());
            System.out.println("The maximum of values is "
                               + intSummaryStatistics.getMax());
            System.out.println("The minimum of values is "
                               + intSummaryStatistics.getMin());
            System.out.println("The string representation is");
            System.out.println(intSummaryStatistics.toString());
        }
    }
    ```

    **Output:**

    ```
    The count of values is 5
    The average of values is 30.0
    The sum of values is 150
    The maximum of values is 50
    The minimum of values is 10
    The string representation is
    IntSummaryStatistics{count=5, sum=150, min=10, average=30.000000, max=50}

    ```

    **参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/intsummarystatistics . html](https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html)