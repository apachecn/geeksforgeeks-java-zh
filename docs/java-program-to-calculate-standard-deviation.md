# 计算标准差的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-计算程序-标准偏差/](https://www.geeksforgeeks.org/java-program-to-calculate-standard-deviation/)

**标准偏差**是衡量数字分布的标准。它的符号是西格玛 **(** **σ)。**是方差的平方根。任务是计算一些数字的标准差。

考虑一个由 6 个数字组成的例子，然后为了计算标准差，首先我们需要计算 6 个数字的总和，然后计算平均值。然后使用标准差公式计算标准差。

```java
Standard deviation = square root of ∑(X<sub>i</sub> - ų)<sup>2</sup> / N 
              where, 
                Xi = each element of the array
                ų = mean of the elements of the array
                N = Number of elements
                ∑ = Sum of the each element
```

```java
Input : [12, 32, 11, 55, 10, 23, 14, 30]
Output : 14.438988

Input : [10, 12, 22, 34, 21]
Output : 8.541663
```

**方法:使用数学公式**

1.  首先，创建一个名为**计算 2** 的类
2.  然后创建 main 方法，然后在 main 方法中创建上述类的一个对象，并使用该对象调用它。
3.  然后用上面例子中给出的值在这个类中声明一个数组。
4.  现在，为了遍历数组，我们需要找到数组的大小。
5.  现在，使用 for 循环遍历这个数组，并将其增加 1，因为我们需要打印数组的所有元素。
6.  然后，再次使用 for 循环迭代数组，以计算数组元素的总和。
7.  之后，平均值将通过平均值=和/ n 来计算，其中 n 是数组中的元素数量。
8.  现在，标准偏差将在平均值的帮助下计算，这是通过再次迭代 for-loop 并在数学预定义方法(如 Math.pow 和 Math.sqrt)的帮助下完成的
9.  之后，该类将返回该值，然后打印。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to calculate the standard deviation

class calculateSD2 {
    double sum = 0.0;
    double standardDeviation = 0.0;
    double mean = 0.0;
    double res = 0.0;
    double sq = 0.0;

    double SD()
    {
        int[] arr = { 12, 32, 11, 55, 10, 23, 14, 30 };
        int n = arr.length;

        System.out.println("Elements are:");
        for (int i = 0; i < n; i++) {
            System.out.println(arr[i]);
        }

        for (int i = 0; i < n; i++) {
            sum = sum + arr[i];
        }

        mean = sum / (n);

        for (int i = 0; i < n; i++) {

            standardDeviation
                = standardDeviation + Math.pow((arr[i] - mean), 2);

        }

        sq = standardDeviation / n;
        res = Math.sqrt(sq);
        return res;
    }
}

public class Standard {
    public static void main(String[] args)
    {

        calculateSD2 calsd = new calculateSD2();
        double res = calsd.SD();

        System.out.format("Standard Deviation = %.6f", res);
    }
}
```

**Output**

```java
Elements are:
12
32
11
55
10
23
14
30
Standard Deviation = 14.438988
```