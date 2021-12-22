# Java 中的 BigInteger 等于()方法

> 原文:[https://www . geesforgeks . org/big integer-equals-method-in-Java/](https://www.geeksforgeeks.org/biginteger-equals-method-in-java/)

**Java . math . BigInteger . equals(Object x)**方法将此 BigInteger 与作为参数传递的对象进行比较，如果两者的值相等，则返回 true，否则返回 false。

**语法:**

```
public boolean equals(Object x)
```

**参数:**该方法接受单个强制参数 **x** ，该参数是要与大整数对象进行比较的对象。

**返回:**当且仅当作为参数传递的对象是一个大整数，其值等于应用该方法的大整数对象时，该方法返回布尔值 true。否则将返回 false。

**例:**

```
Input: BigInteger1=2345, BigInteger2=7456
Output: false
Explanation: BigInteger1.equals(BigInteger2)=false.

Input: BigInteger1=7356, BigInteger2=7456
Output: true
Explanation: BigInteger1.equals(BigInteger2)=true.

```

下面的程序说明了 BigInteger 类的 equals()方法:

**例 1:** 两者价值相等时。

```
// Java program to demonstrate equals() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("321456");
        b2 = new BigInteger("321456");

        // apply equals() method
        boolean response = b1.equals(b2);

        // print result
        if (response) {

            System.out.println("BigInteger1 " + b1
                               + " and BigInteger2 "
                               + b2 + " are equal");
        }
        else {

            System.out.println("BigInteger1 " + b1
                               + " and BigInteger2 "
                               + b2 + " are not equal");
        }
    }
}
```

**输出:**

```
BigInteger1 321456 and BigInteger2 321456 are equal

```

**例 2:** 两者价值不相等时。

```
// Java program to demonstrate equals() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {

        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("321456");
        b2 = new BigInteger("456782");

        // apply equals() method
        boolean response = b1.equals(b2);

        // print result
        if (response) {

            System.out.println("BigInteger1 " + b1
                               + " and BigInteger2 "
                               + b2 + " are equal");
        }
        else {

            System.out.println("BigInteger1 " + b1
                               + " and BigInteger2 " + b2 + " are not equal");
        }
    }
}
```

**输出:**

```
BigInteger1 321456 and BigInteger2 456782 are not equal

```

**示例 3:** 当作为参数传递的对象不是大整数时。

```
// Java program to demonstrate equals() method of BigInteger

import java.math.BigInteger;

public class Main6 {

    public static void main(String[] args)
    {

        // Creating  BigInteger object
        BigInteger b1;

        b1 = new BigInteger("321456");
        String object = "321456";

        // apply equals() method
        boolean response = b1.equals(object);

        // print result
        if (response) {

            System.out.println("BigInteger1 " + b1
                               + " and String Object "
                               + object + " are equal");
        }
        else {

            System.out.println("BigInteger1 " + b1
                               + " and String Object "
                               + object + " are not equal");
        }
    }
}
```

**输出:**

```
BigInteger1 321456 and String Object 321456 are not equal

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/biginteger . html # equals(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#equals(java.lang.Object))