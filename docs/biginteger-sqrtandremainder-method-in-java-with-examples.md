# Java 中的大整数 sqrtAndRemainder()方法，带示例

> 原文:[https://www . geesforgeks . org/big integer-sqrtandreminder-method-in-Java-with-examples/](https://www.geeksforgeeks.org/biginteger-sqrtandremainder-method-in-java-with-examples/)

java.math.BigInteger 。sqrtAndRemainder()方法对调用此方法的当前 BigInteger 执行操作。这个方法是用来计算这个数的**整数平方根** (sqrt(this))以及这个数的余数与平方。它返回一个由两个大整数组成的数组，这两个大整数分别包含这个整数的平方根“p”及其余数(这个–p * p)。BigInteger 类内部使用整数数组进行处理，因此对 big integer 对象的操作不如对原语的操作快。

**注:**此方法自 **JDK 9** 起可用

**语法:**

```java
public BigInteger[] sqrtAndRemainder()

```

**参数:**该方法不接受参数。

**返回值:**这个方法返回两个大整数的数组，整数平方根在索引 0，余数在索引 1。

**异常:**数值必须为正数，否则[算法异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)被抛出。

**下面的程序说明了 BigInteger 类**的 sqrtAndRemainder()方法

**例 1:**

```java
// Java program to demonstrate
// sqrtAndRemainder() method of BigInteger

import java.math.BigInteger;

class Main {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger res[];

        // For user input
        // Use Scanner or BufferedReader

        // Two object of String created
        // Holds the values to perform operation
        String input1 = "15";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);

        // Using sqrtAndRemainder() method
        try {

            res = a.sqrtAndRemainder();

            // Display the result
            System.out.println("The square root of\n"
                               + a + "\nis " + res[0]
                               + "\nand remainder is "
                               + res[1]);
        }
        catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
The square root of
15
is 3
and remainder is 6

```

**例 2:**

```java
// Java program to demonstrate
// sqrtAndRemainder() method of BigInteger

import java.math.BigInteger;

class Main {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger res[];

        // For user input
        // Use Scanner or BufferedReader

        // Two object of String created
        // Holds the values to perform operation
        String input1 = "625";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);

        // Using sqrtAndRemainder() method
        try {

            res = a.sqrtAndRemainder();

            // Display the result
            System.out.println("The square root of\n"
                               + a + "\nis " + res[0]
                               + "\nand remainder is "
                               + res[1]);
        }
        catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
The square root of
625
is 25
and remainder is 0

```

**例 3:**
数值为负时显示异常的程序。

```java
// Java program to demonstrate
// sqrtAndRemainder() method of BigInteger

import java.math.BigInteger;

class Main {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger res[];

        // For user input
        // Use Scanner or BufferedReader

        // Two object of String created
        // Holds the values to perform operation
        String input1 = "-9";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);

        // Using sqrtAndRemainder() method
        try {

            res = a.sqrtAndRemainder();

            // Display the result
            System.out.println("The square root of\n"
                               + a + "\nis " + res[0]
                               + "\nand remainder is "
                               + res[1]);
        }
        catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.ArithmeticException: Negative BigInteger

```

**参考资料:**[https://docs . Oracle . com/javae/9/docs/API/Java/math/big integer . html # sqrtandemainder--](https://docs.oracle.com/javase/9/docs/api/java/math/BigInteger.html#sqrtAndRemainder--)