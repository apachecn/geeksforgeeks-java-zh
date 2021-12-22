# IntSummaryStatistics to string()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/intsummarystatistics-to string-method-in-Java-with-examples/](https://www.geeksforgeeks.org/intsummarystatistics-tostring-method-in-java-with-examples/)

Java 中 **IntSummaryStatistics 类的 **toString()** 方法用于获取该 IntSummaryStatistics 中记录的字符串表示。**

**语法:**

```java
public long toString()

```

**参数:**此方法不接受任何值作为参数。

**返回值:**该方法返回 IntSummaryStatistics 中记录的字符串表示形式。

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

        Iterator<Integer> iterator
            = list.listIterator();
        while (iterator.hasNext()) {

            // Add the integers to the IntSummaryStatistics object
            intSummaryStatistics.accept(iterator.next());
        }

        System.out.println("The String representation of values is \n"
                           + intSummaryStatistics.toString());
    }
}
```

**输出:**

```java
The String representation of values is IntSummaryStatistics
{count=5, sum=150, min=10, average=30.000000, max=50}

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/intsummarystatistics . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/util/IntSummaryStatistics.html#toString())