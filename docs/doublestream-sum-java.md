# Java 中的 DoubleStream sum()

> 原文:[https://www.geeksforgeeks.org/doublestream-sum-java/](https://www.geeksforgeeks.org/doublestream-sum-java/)

**DoubleStream sum()** 返回该流中元素的总和。这是**减**的特例。DoubleStream sum()是一个 ***终端操作*** ，也就是说，它可能遍历该流以产生结果或副作用。

**注:**约简操作(也称为折叠)取一系列输入元素，通过重复应用组合操作(如求一组数字的和或最大值)将它们组合成单个汇总结果。

**语法:**

```java
double sum()

```

**返回值:**函数返回该流中元素的总和。

**注:**

1.  如果任何流元素是 NaN 或者总和在任何点都是 NaN，那么总和将是 NaN。
2.  按绝对值递增排序的元素往往会产生更准确的结果。

**例 1 :**

```java
// Java code for DoubleStream.sum() to
// find the sum of elements in DoubleStream
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(2.2, 4.3, 6.4,
                                              -2.5, -4.6);

        // Using DoubleStream.sum() to find
        // sum of elements in DoubleStream
        double sumOfElements = stream.sum();

        // Displaying the calculated sum
        System.out.println(sumOfElements);
    }
}
```

**Output:**

```java
5.800000000000001

```

**例 2 :**

```java
// Java code for DoubleStream.sum() to
// find the sum of elements
// greater than 2.5
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        // Using DoubleStream.sum() to find
        // sum of elements greater than 2.5
        double sumOfElements = DoubleStream.of(2.2, 4.2, 6.4,
                                               -2.5, -4.5)
                                   .filter(num -> num > 2.5)
                                   .sum();

        // Displaying the calculated sum
        System.out.println(sumOfElements);
    }
}
```

**Output:**

```java
10.600000000000001

```