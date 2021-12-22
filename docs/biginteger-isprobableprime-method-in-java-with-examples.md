# Java 中的 BigInteger isProbablePrime()方法，带示例

> 原文:[https://www . geesforgeks . org/big integer-isrobableprime-in-Java-method-with-examples/](https://www.geeksforgeeks.org/biginteger-isprobableprime-method-in-java-with-examples/)

**T1。isrobablePrime(int 确定性)**方法用来判断这个 BigInteger 可能是 prime 还是绝对是 composite。此方法检查调用此方法的当前 BigInteger 上的质数或合成数，并返回一个布尔值。如果这个大整数可能是质数，它返回真，如果它肯定是复合的，它返回假。如果确定性为< = 0，则返回真。

**语法:**

```
public boolean isProbablePrime(int certainty)
```

**参数:**该方法接受一个强制参数**确定性**，它是用户可接受的不确定性的度量。这是因为 BigInteger 是一个非常非常大的数字，准确地找到它是否是质数是非常困难和昂贵的。因此，可以说这种方法基于阈值(1–1/2<sup>确定性</sup>)来检查这个大整数的素数。

**返回值:**这个方法返回一个布尔值，说明这个大整数是否是质数。如果这个大整数可能是质数，它返回真，如果它肯定是复合的，它返回假。

下面的程序是用来说明 BigInteger 的 isProbablePrime()方法的。

**例 1:**

```
// Java program to demonstrate
// isProbablePrime() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // Boolean variable to store the result
        boolean result;

        // Creates one BigInteger object
        BigInteger a
            = new BigInteger(
                "95848961698036841689418631330196");

        // When certainty is one,
        // it will check number for prime or composite
        result = a.isProbablePrime(1);
        System.out.println(a.toString()
                           + " with certainty 1 "
                           + result);

        // When certainty is zero,
        // it is always true
        result = a.isProbablePrime(0);
        System.out.println(a.toString()
                           + " with certainty 0 "
                           + result);

        // When certainty is negative,
        // it is always true
        result = a.isProbablePrime(-1);
        System.out.println(a.toString()
                           + " with certainty -1 "
                           + result);
    }
}
```

**输出:**

```
95848961698036841689418631330196 with certainty 1 false
95848961698036841689418631330196 with certainty 0 true
95848961698036841689418631330196 with certainty -1 true

```

**例 2:**

```
// Java program to demonstrate
// isProbablePrime() method of BigInteger

import java.math.BigInteger;

public class GFG {
    public static void main(String[] args)
    {

        // Boolean variable to store the result
        boolean result;

        // Creates one BigInteger object
        BigInteger a
            = new BigInteger(
                "654561561356879113561");

        // When certainty is one,
        // it will check number for prime or composite
        result = a.isProbablePrime(1);
        System.out.println(a.toString()
                           + " with certainty 1 "
                           + result);

        // When certainty is zero,
        // it is always true
        result = a.isProbablePrime(0);
        System.out.println(a.toString()
                           + " with certainty 0 "
                           + result);

        // When certainty is negative,
        // it is always true
        result = a.isProbablePrime(-1);
        System.out.println(a.toString()
                           + " with certainty -1 "
                           + result);
    }
}
```

**输出:**

```
654561561356879113561 with certainty 1 false
654561561356879113561 with certainty 0 true
654561561356879113561 with certainty -1 true

```

**参考:**[https://docs . Oracle . com/javae/9/docs/API/Java/math/biginteger . html # ispbleprime(int)](https://docs.oracle.com/javase/9/docs/api/java/math/BigInteger.html#isProbablePrime(int))