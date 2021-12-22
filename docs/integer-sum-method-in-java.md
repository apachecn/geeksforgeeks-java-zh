# Java 中的整数和()方法

> 原文:[https://www.geeksforgeeks.org/integer-sum-method-in-java/](https://www.geeksforgeeks.org/integer-sum-method-in-java/)

java.lang.Integer.sum()是 java 中的一个内置方法，它返回其参数的总和。该方法根据+运算符将两个整数相加。

**语法:**

```
public static int sum(*int a, int b*)
```

**参数:**该方法接受两个要相互相加的参数:
T3】a:第一个整数值。
*b* :第二个整数值。

**返回值:**该方法返回其参数之和。
**异常:**当结果溢出一个整数时，该方法抛出*算术异常*。

**示例**

```
Input: a = 170, b = 455
Output: 625

Input: a = 45, b = 45
Output: 90
```

下面的程序说明了 Java.lang.Integer.sum()方法:
**程序 1:** 为正数。

```
// Java program to illustrate the
// Java.lang.Integer.sum() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {
        int a = 62;
        int b = 18;
        // It will return the sum of two arguments.
        System.out.println("The sum is =" + Integer.sum(a, b));
    }
}
```

**Output:**

```
The sum is =80

```

**程序 2:** 下面的程序说明了异常。

```
// Java program to illustrate the
// Java.lang.Integer.sum() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {
        // When very large integer is taken
        int a = 92374612162; 
        int b = 181;
        // It will return the sum of two arguments.
        System.out.println("The sum is =" + Integer.sum(a, b));
    }
}
```

**Output:**

```
prog.java:8: error: integer number too large: 92374612162
       int a = 92374612162;
               ^
1 error

```