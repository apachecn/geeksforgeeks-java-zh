# Java 中的大整数下一个概率素()方法，示例

> 原文:[https://www . geesforgeks . org/big integer-nextprobleprime-method-in-Java-with-examples/](https://www.geeksforgeeks.org/biginteger-nextprobableprime-method-in-java-with-examples/)

T2。nextProbablePrime()用于查找第一个可能是素数的大于这个 BigInteger 的整数。如果这个方法返回“p”，那么在这个大整数和“p”(这个< q < p)之间没有质数“q”，也就是说，它从不跳过任何大于用来调用这个方法的大整数的质数。

**语法:**

```
public BigInteger nextProbablePrime()

```

**参数:**该方法不接受任何参数。
**Return:** 这个方法返回一个 Biginteger，这个 BigInteger 保存的第一个大于这个 big integer 的整数可能是质数。

**异常:**数值必须非负且不要太大，否则抛出 **[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)** 。

**下面的程序说明了大整数类**的 next 概率 Prime()方法

**例 1:**

```
// Java program to demonstrate
// nextProbablePrime() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // BigInteger object to store the result
        BigInteger result;

        // For user input
        // Use Scanner or BufferedReader

        // object of String created
        // Holds the value to find next prime number
        String input1 = "1516132";

        // Creating BigInteger object
        BigInteger a
            = new BigInteger(input1);

        // Using nextProbablePrime()
        result = a.nextProbablePrime();

        // Print result
        System.out.println("The next probable"
                           + " Prime number is "
                           + result);
    }
}
```

**Output:**

```
The next probable Prime number is 1516153

```

**示例 2:** 打印所有 100 以下的质数

```
// Java program to demonstrate
// nextProbablePrime() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // BigInteger object to store the result
        BigInteger result;

        // Creating BigInteger objects
        BigInteger a;

        // Printing all prime numbers
        // Below 100
        for (int i = 0; i < 100😉 {
            a = new BigInteger(
                Integer.toString(i));

            // Using nextProbablePrime()
            result = a.nextProbablePrime();

            // Print the answer
            if (Integer.parseInt(
                    result.toString())
                < 100) {
                System.out.print(result + " ");
            }

            i = Integer.parseInt(
                result.toString());
        }
    }
}
```

**Output:**

```
2 3 5 7 11 13 17 19 23 29 31 37 41 43 47 53 59 61 67 71 73 79 83 89 97

```

**例 3:** 数值为负时显示异常的程序。

```
// Java program to demonstrate
// nextProbablePrime() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // BigInteger object to store the result
        BigInteger result;

        // For user input
        // Use Scanner or BufferedReader

        // object of String created
        // Holds the value to find prime number
        String input1 = "-5";

        // Creating BigInteger objects
        BigInteger a
            = new BigInteger(input1);

        try {
            // Using nextProbablePrime()
            result = a.nextProbablePrime();
        }
        catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```
java.lang.ArithmeticException: start < 0: -5

```

要了解检查当前 BigInteger 是否是素数，请访问[Java 中的 isProbablePrime()方法](https://www.geeksforgeeks.org/biginteger-isprobableprime-method-in-java-with-examples/)页面。

**参考:**[https://docs . Oracle . com/en/Java/javae/12/docs/API/Java . base/Java/math/big integer . html # nextprobable prime()](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#nextProbablePrime())