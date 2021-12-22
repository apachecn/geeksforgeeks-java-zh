# 在 Java 中使用中间平方法生成随机数

> 原文:[https://www . geeksforgeeks . org/generate-random-numbers-use-mid-square-in-Java 方法/](https://www.geeksforgeeks.org/generate-random-numbers-using-middle-square-method-in-java/)

这种方法是由范·诺依曼提出的。在这种方法中，我们有一个种子，然后种子被平方，它的中期作为随机数取出。假设我们有一个种子，它有 N 个数字，我们对这个数字进行平方，得到一个 2N 个数字，如果它没有变成 2N 个数字，我们在这个数字前面加零，使它变成 2N 个数字。一个好的算法基本上是一个不依赖于种子的算法，周期也应该是最长的，在它开始重复自己之前，它应该几乎触及它范围内的每个数字。作为经验法则，记住周期越长，数字越随机。

**例:**

```java
Consider the seed to be 14 and we want a two digit random number.
Number --> Square --> Mid-term
14     --> 0196   --> 19 
19     --> 0361   --> 36
36     --> 1296   --> 29
29     --> 0841   --> 84
84     --> 7056   --> 05
05     --> 0025   --> 02
02     --> 0004   --> 00
00     --> 0000   --> 00 
```

在上面的例子中，我们可以注意到我们得到了一些随机数 19，36，29，84，05，02，00，它们似乎是随机选择的，这样我们得到了多个随机数，直到我们遇到一个自重复链。我们也知道了这种方法的一个缺点，如果我们遇到 0，那么我们会从那个点得到一串 0。此外，考虑我们得到一个随机数 50，平方将是 2500，期中又是 50，我们进入这个 50 的链，有时我们可能会更经常地遇到这样的链，这是一个缺点，由于这些缺点，这种方法实际上不能用于生成随机数。

实现:

## Java

```java
// Generate Random Numbers Using Middle
// Square Method in Java
import java.util.Random;

public class Main {
    static int rangeArray[]
        = { 1,      10,      100,      1000,     10000,
            100000, 1000000, 10000000, 100000000 };
    // function for generating a random number
    static long middleSquareNumber(long num, int digit)
    {
        long sqn = num * num, nextNum = 0;
        int trim = (digit / 2);
        sqn = sqn / rangeArray[trim];
        for (int i = 0; i < digit; i++) {
            nextNum += (sqn % (rangeArray[trim]))
                       * (rangeArray[i]);
            sqn = sqn / 10;
        }
        return nextNum;
    }
    public static void main(String args[])
    {
        int numberOfDigit = 3;
        int start = rangeArray[numberOfDigit - 1],
            end = rangeArray[numberOfDigit];
        // create rand object
        Random rand = new Random();
        long nextNumber = rand.nextInt(end - start) + start;
        System.out.print(
            "The random numbers for the Geeks are:\n"
            + nextNumber + ", ");
        // Generating 10 random numbers
        for (int i = 0; i < 9; i++) {
            nextNumber = middleSquareNumber(nextNumber,
                                            numberOfDigit);
            System.out.print(nextNumber + ", ");
        }
    }
}
```

**输出**

```java
The random numbers for the Geeks are:
325, 562, 584, 105, 102, 40, 160, 560, 360, 960, 
```

**注意:**上面的程序展示了 Middle Square Number 方法是如何工作的，你可以多次运行程序来查看每次生成的不同随机数。由于其缺点，不建议将这种方法作为生成随机数的理想方法，但是这种方法也可以用作散列算法和一些其他应用。