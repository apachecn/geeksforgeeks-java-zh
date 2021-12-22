# Java 中的 BigInteger 除()方法，示例

> 原文:[https://www . geesforgeks . org/big integer-divide-in-Java-method-with-examples/](https://www.geeksforgeeks.org/biginteger-divide-method-in-java-with-examples/)

**T1 大整数。divide(BigInteger val)** 用于计算两个 BigInteger 的除法。BigInteger 类内部使用整数数组进行处理，对 big integer 对象的操作没有对原语的操作快。此方法对调用此方法的当前大整数执行操作，并将大整数作为参数传递。

**语法:**

```java
public BigInteger divide(BigInteger val)

```

**参数:**这个方法接受一个参数**值**，这个值就是这个大整数的除数。

**返回值:**这个方法返回一个大整数，它保存整数(非浮点值)中的除法(this / val)，也就是说，它将结果舍入到它的最低值。

**异常:**参数 val 不能为 0，否则抛出 **[算术异常](https://www.geeksforgeeks.org/types-of-exception-in-java-with-examples/)** 。

**下面的程序用来说明 BigInteger 的 divide()方法。**

**例 1:**

```java
// Java program to demonstrate
// divide() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger div;

        // Two objects of String created
        // Holds the values to calculate the division
        String input1 = "400000000000000000"
                        + "000000000000000000";

        String input2 = "8000000";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Using divide() method
        div = a.divide(b);

        // Display the result in BigInteger
        System.out.println("The division of\n"
                           + a + " \nby\n" + b + " "
                           + "\nis\n" + div);
    }
}
```

**输出:**

```java
The division of
400000000000000000000000000000000000 
by
8000000 
is
50000000000000000000000000000

```

**示例 2:** 演示如何舍入结果

```java
// Java program to demonstrate
// divide() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger div;

        // Two objects of String created
        // Holds the values to calculate the division
        String input1 = "456216545";

        String input2 = "21255132";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Using divide() method
        div = a.divide(b);

        // Display the result in BigInteger
        System.out.println("The division of\n"
                           + a + " \nby\n" + b + " "
                           + "\nis " + div);

        double d = Double.parseDouble(input1)
                   / Double.parseDouble(input2);

        // Display result in double type
        // To match both the results
        System.out.print("Using double result is " + d);
    }
}
```

**输出:**

```java
The division of
456216545 
by
21255132 
is 21
Using double result is 21.46383024109189

```

**示例 3:** 演示被 0 除时抛出的异常

```java
// Java program to demonstrate
// divide() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {
        // BigInteger object to store result
        BigInteger div;

        // Two objects of String created
        // Holds the values to calculate the division
        String input1 = "456216545"
                        + "452133155";

        String input2 = "0";

        // Convert the string input to BigInteger
        BigInteger a
            = new BigInteger(input1);
        BigInteger b
            = new BigInteger(input2);

        // Using divide() method
        try {
            div = a.divide(b);

            // Display the result in BigInteger
            System.out.println("The division of\n"
                               + a + " \nby\n" + b + " "
                               + "\nis\n" + div + "\n");
        }
        catch (ArithmeticException e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.ArithmeticException: BigInteger divide by zero

```

**参考:**[https://docs . Oracle . com/en/Java/javae/12/docs/API/Java . base/Java/math/big integer . html # divide(Java . math . big integer)](https://docs.oracle.com/en/java/javase/12/docs/api/java.base/java/math/BigInteger.html#divide(java.math.BigInteger))