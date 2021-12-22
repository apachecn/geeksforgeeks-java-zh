# Java 中的 BigDecimal 精度()方法

> 原文:[https://www . geesforgeks . org/big decimal-precision-method-in-Java/](https://www.geeksforgeeks.org/bigdecimal-precision-method-in-java/)

**Java . math . BigDecimal . precision()**方法返回*这个* BigDecimal 的精度。精度是指未缩放值中的位数。

**语法:**

```java
public int precision()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个整数，表示*这个*大十进制对象的精度。

**示例:**

```java
Input : 198.176
Output : 6

Input : 721111.111
Output : 9

```

下面的程序说明了 java 中的 java.math.BigDecimal.precision()函数:
**程序 1:**

```java
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // create 2 BigDecimal Objects
        BigDecimal b1, b2;

        // Assigning values to b1, b2
        b1 = new BigDecimal("198.176");
        b2 = new BigDecimal("721111.111");

        // Display their respective precision
        System.out.println("The precision of " + b1 + " is " + b1.precision());
        System.out.println("The precision of " + b2 + " is " + b2.precision());
    }
}
```

**Output:**

```java
The precision of 198.176 is 6
The precision of 721111.111 is 9

```

**程序 2:**

```java
// Java program to illustrate
// precision() Function
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating a BigDecimal Object
        BigDecimal num;

        // Assigning value 0.1 + 0.1 + 0.1 to num
        num = new BigDecimal("0.1")
                  .add(new BigDecimal("0.1"))
                  .add(new BigDecimal("0.1"));

        // Display the BigDecimal value and its precision
        System.out.println("The precision of " + num + " is "
        + num.precision());
    }
}
```

**Output:**

```java
The precision of 0.3 is 1

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/bigdecimal . html # precision()](https://docs.oracle.com/javase/7/docs/api/java/math/BigDecimal.html#precision())