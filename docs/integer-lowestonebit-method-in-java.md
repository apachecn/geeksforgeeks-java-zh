# Java 中的整数 lowestOneBit()方法

> 原文:[https://www . geesforgeks . org/integer-lowstonbit-method-in-Java/](https://www.geeksforgeeks.org/integer-lowestonebit-method-in-java/)

java.lang 的 Integer.lowestOneBit()方法是一个内置函数，它返回一个最多只有一个一位的 int 值，该值位于指定 int 值中最低(即最右边)一位的位置。如果指定的值在其二进制补码二进制表示中没有一位，即。如果数字的二进制表示等于零。
**语法:**

```
public static int lowestOneBit(*int a*)
```

**参数:**该方法取一个整数类型的参数 *a* ，该参数是指要返回其最低位或要对其执行操作的值。
**返回:**该方法可以返回两种类型的值:

*   返回一个整数值，该整数值位于指定值中最低的一位
*   如果指定值等于零，则返回零。

**示例:**

```
Input: 157
Output: Lowest one bit = 1

Input: 0
Output: Lowest one bit = 0

Explanation:
Consider any integer a = 10
Binary Representation = 0000 1010
Lowest bit(at 1) i.e.0000 0010
so result = 2^1=2
```

下面的程序说明了 Java . lang . integer . lowstonbit()方法:
**程序 1:** 为正数。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.Integer.lowestOneBit() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = 157;
        System.out.println("Given Number = " + a);

        // Returns an int value with at most a single one-bit
        System.out.print("Lowest one bit = ");
        System.out.println(Integer.lowestOneBit(a));

        a = 64;
        System.out.println("Given Number = " + a);

        System.out.print("Lowest one bit = ");
        System.out.println(Integer.lowestOneBit(a));

        // Here it will return 0 since the number is itself zero
        a = 0;
        System.out.println("Given Number = " + a);

        System.out.print("Lowest one bit = ");
        System.out.println(Integer.lowestOneBit(a));
    }
}
```

**Output:** 

```
Given Number = 157
Lowest one bit = 1
Given Number = 64
Lowest one bit = 64
Given Number = 0
Lowest one bit = 0
```

**程序 2:** 为负数。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.Integer.lowestOneBit() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = -157;
        System.out.println("Given Number = " + a);

        // It will return an int value with at most a single one-bit
        System.out.print("Lowest one bit = ");
        System.out.println(Integer.lowestOneBit(a));
        a = -17;
        System.out.println("Given Number = " + a);

        System.out.print("Lowest one bit = ");
        System.out.println(Integer.lowestOneBit(a));
    }
}
```

**Output:** 

```
Given Number = -157
Lowest one bit = 1
Given Number = -17
Lowest one bit = 1
```

**程序 3:** 为十进制值和字符串。
**注意:**当一个十进制值和一个字符串作为参数传递时，它会返回编译时错误消息。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.Integer.lowestOneBit() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        // Decimal value is given
        int a = 71.57;
        System.out.println("Given Number = " + a);

        System.out.print("Lowest one bit = ");
        System.out.println(Integer.lowestOneBit(a));

        // String is passed
        a = "12";
        System.out.println("Given Number = " + a);

        System.out.print("Lowest one bit = ");
        System.out.println(Integer.lowestOneBit(a));
    }
}
```

**输出:**

```
prog.java:10: error: incompatible types: possible lossy conversion from double to int
    int a = 71.57;
            ^
prog.java:17: error: incompatible types: String cannot be converted to int
    a = "12";
        ^
2 errors
```