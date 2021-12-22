# Java 中的 Java.math.BigInteger .概率 Prime()方法

> 原文:[https://www . geesforgeks . org/Java-math-big integer-probability-method-in-Java/](https://www.geeksforgeeks.org/java-math-biginteger-probableprime-method-in-java/)

**先决条件:** [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

概率素数()方法将返回一个长度为素数的大整数位。位长度是作为方法概率的参数提供的，该方法将返回一个由位长度位组成的素数大整数。此方法返回的大整数是复合整数且不超过 2^-100.的概率

**语法:**

```java
public static BigInteger probablePrime(int bitLength, Random rnd)
```

**参数:**该方法接受两个参数，如上语法所示，如下所述。

*   **位长**–返回的大整数的位长。
*   **rnd**–随机位的来源，用于选择候选项进行素性测试。

**返回值:**这个方法返回一个可能是素数的*位长*位的大整数。

**异常:**

*   **Arithmetic exception** -If the bit length < is 2.

下面的程序说明了概率犯罪()方法:

```java
import java.math.*;
import java.util.Random;
import java.util.Scanner;

public class GFG {

    public static void main(String[] args)
    {

        Scanner sc = new Scanner(System.in);

        // create a BigInteger object
        BigInteger biginteger;

        // create a integer value for bitLength
        int length = 4;

        // create a random object
        Random random = new Random();

        // call probablePrime method to find next probable prime
        // whose bit length is equal to bitLength provided as parameter.
        biginteger = BigInteger.probablePrime(length, random);

        String result = "ProbablePrime whose bit length is "
                        + length + " = " + biginteger;

        // print result value
        System.out.println(result);
    }
}
```

**输出** :

```java
ProbablePrime whose bit length is 4 = 13

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/math/big integer . html # probable prime(int，%20java.util.Random)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#probablePrime(int, %20java.util.Random))