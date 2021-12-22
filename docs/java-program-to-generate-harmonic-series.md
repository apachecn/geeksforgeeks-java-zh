# 生成调和级数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序生成谐波系列/](https://www.geeksforgeeks.org/java-program-to-generate-harmonic-series/)

调和级数是算术级数的倒数。一般来说，a [调和级数](https://www.geeksforgeeks.org/harmonic-progression/)中的术语可以表示为

> h1 = 1/a，h2 = 1/(a+d)，h3 = 1/(a+2d)，H4 = 1/(a+3d)………..，hn = 1/(a+nd)。

其中 **h** 为调和级数， **a** 为[等差数列](https://www.geeksforgeeks.org/arithmetic-progression/)**d**为等差数列与 **n** 之间的[公差](https://www.geeksforgeeks.org/arithmetic-progression-common-difference-and-nth-term-class-10-maths/)为第 n 项。

**例 1:(使用 while 循环)**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Generate Harmonic Series

class HarmonicSeries {

    // this is a main function
    public static void main(String args[])
    {

        // num is the number of values we want in a series
        int num = 5;
        double result = 0.0;

        System.out.println("The harmonic series is: ");

        // printing the harmonic series till num value
        // using while loop
        while (num > 0) {

            // calculating harmonic values
            result = result + (double)1 / num;

            // after calculating harmonic value
            // decrementing num by 1 which means the common
            // difference is 1
            num--;
            System.out.print(result + ", ");
        }
    }
}
```

**Output**

```
The harmonic series is: 
0.2, 0.45, 0.7833333333333333, 1.2833333333333332, 2.283333333333333,
```

**例 2:(用于循环)**

## Java

```
// Java Program to Generate Harmonic Series

class HarmonicSeries {

    // this is a main function
    public static void main(String args[])
    {

        // num is the number of values we want in a series
        int num = 5;
        double result = 0.0;

        System.out.println("The harmonic series is: ");

        // printing the harmonic series till num value
        // using for loop
        for (int i = num; i > 0; i--) {

            // calculating harmonic values
            result = result + (double)1 / i;
            System.out.print(result + ", ");
        }
    }
}
```

**输出**

```
The harmonic series is: 
0.2, 0.45, 0.7833333333333333, 1.2833333333333332, 2.283333333333333,
```

**例 3:**

## 爪哇

```
// Java Program to Generate Harmonic Series

// importing necessary java packages
import java.util.Scanner;
import java.lang.*;

class HarmonicSeries {

    // this is a main function
    public static void main(String args[])
    {

        // scanner class is a pre-defined class in java
        // for taking input from keyboard
        Scanner in = new Scanner(System.in);

        System.out.print("Enter Number: ");

        // storing input value in num
        int num = in.nextInt();
        double result = 0.0;

        System.out.println("The harmonic series is: ");

        // printing the harmonic series till num value
        // using for loop
        for (int i = num; i > 0; i--) {

            // calculating harmonic values
            result = result + (double)1 / i;

            System.out.print(result + ", ");
        }
    }
}
```

**输出**

```
$ javac HarmonicSeries.java
$ java HarmonicSeries

Enter Number: 5
The harmonic series is: 
0.2, 0.45, 0.7833333333333333, 1.2833333333333332, 2.283333333333333
```

```
$ javac HarmonicSeries.java
$ java HarmonicSeries

Enter Number: 6
The harmonic series is: 
0.16666666666666666, 0.3666666666666667, 0.6166666666666667, 0.95, 1.45, 2.45
```