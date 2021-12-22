# Java 中的 Java . math . biginteger . modiinverse()方法

> 原文:[https://www . geesforgeks . org/Java-math-big integer-modi inverse-method-in-Java/](https://www.geeksforgeeks.org/java-math-biginteger-modinverse-method-in-java/)

**先决条件:** [大整数基础知识](https://www.geeksforgeeks.org/biginteger-class-in-java/)

modPow()方法返回这个 mod m 的模乘逆，如果 m <= 0 或者这个没有乘逆 mod m(即 gcd(this，m)！= 1).

**语法:**

```java
public BigInteger modInverse(BigInteger m)
```

**参数:**m–模量。

**返回值:**这个方法返回一个 BigInteger 对象，其值为((this)^(-1) mod m)。

**异常:**

*   **Arithmetic exception** –m < = 0, or this BigInteger has no multiplicative inverse mod m (that is, this BigInteger is not prime relative to m).

下面的程序说明了 BigInteger.modInverse()方法:

**节目 1** :

```java
import java.math.*;
import java.util.Scanner;

public class GFG {

    public static void main(String[] args)
    {

        Scanner sc = new Scanner(System.in);

        // create 2 BigInteger objects
        BigInteger biginteger1, biginteger2, result;

        // Initialize all BigInteger Objects
        biginteger1 = new BigInteger("8");
        biginteger2 = new BigInteger("21");

        // perform modInverse operation on biginteger1 using biginteger2.
        result = biginteger1.modInverse(biginteger2);

        String expression = biginteger1 + " ^ -1 % "
                            + biginteger2 + " = " + result;

        // print result value
        System.out.println(expression);
    }
}
```

**输出** :

```java
8 ^ -1 % 21 = 8

```

**节目 2 :**

```java
import java.math.*;
import java.util.Scanner;

public class GFG {

    public static void main(String[] args)
    {

        Scanner sc = new Scanner(System.in);

        // create 2 BigInteger objects
        BigInteger biginteger1, biginteger2, result;

        // Initialize all BigInteger Objects
        biginteger1 = new BigInteger(88882);
        biginteger2 = new BigInteger(22224);

        // perform modInverse operation on biginteger1 using biginteger2.
        result = biginteger1.modInverse(biginteger2);

        String expression = biginteger1 + " ^ -1 % "
                            + biginteger2 + " = " + result;

        // print result value
        System.out.println(expression);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.ArithmeticException: BigInteger not invertible.
    at java.math.MutableBigInteger.modInverse(Unknown Source)
    at java.math.MutableBigInteger.mutableModInverse(Unknown Source)
    at java.math.BigInteger.modInverse(Unknown Source)
    at BigInteger.GFG2.main(GFG2.java:23)

```

**参考:**[https://docs . Oracle . com/javae/7/docs/API/Java/math/big integer . html # modverse(Java . math . big integer)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#modInverse(java.math.BigInteger))