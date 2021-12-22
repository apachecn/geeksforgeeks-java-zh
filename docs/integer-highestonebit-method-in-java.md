# Java 中的整数 highestOneBit()方法

> 原文:[https://www . geeksforgeeks . org/integer-higheestonebit-method-in-Java/](https://www.geeksforgeeks.org/integer-highestonebit-method-in-java/)

java.lang 的 Integer.highestOneBit()方法返回一个最多只有一个一位的整数值，该整数值位于给定 int 值的最高阶(即最左边)一位的位置。如果指定的值在其二进制补码二进制表示中没有一位，那么它返回零，只要它等于零。
**语法:**

```
public static int highestOneBit(*int a*)
```

**参数:**该方法取一个整数类型的参数 *a* ，该参数是指要返回其最高位的值或要对其执行操作的值。
**返回:**该方法可以返回两种类型的值:

*   返回一个整数值，该整数值位于指定值中最高阶的一位
*   如果指定值等于零，则返回零。

**示例:**

```
Input: 19
Output: Highest one bit of the given integer is = 16

Input: -9
Output: Highest one bit of the given integer is = -2147483648

Explanation:
Consider any integer a = 19
Binary Representation = 0001 0011
Highest bit(at 4) i.e.0001 0000
so result = 2^4=16
```

下面的程序说明了 Java . lang . integer . highestonebit()方法。
**程序 1:** 为正数。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// Java.lang.Integer.highestOneBit() Method
import java.lang.*;

public class HighestOneBit {

    public static void main(String[] args)
    {

        int a = 29;
        System.out.println("Number is = " + a);

        // returns an int value with at most a single one-bit, in the position
        // of the highest-order or the leftmost one-bit in the specified int value
        System.out.print("Highest one bit of the given integer is = ");
        System.out.println(Integer.highestOneBit(a));
        a = 44;
        System.out.println("Number is = " + a);
        System.out.print("Highest one bit of the given integer is = ");
        System.out.println(Integer.highestOneBit(a));
    }
}
```

**Output:** 

```
Number is = 29
Highest one bit of the given integer is = 16
Number is = 44
Highest one bit of the given integer is = 32
```

**程序 2:** 为负数。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// Java.lang.Integer.highestOneBit() Method
import java.lang.*;

public class HighestOneBit {

    public static void main(String[] args)
    {

        int a = -9;
        System.out.println("Number is = " + a);

        // returns an int value with at most a single one-bit, in the position
        // of the highest-order or the leftmost one-bit in the specified int value
        System.out.print("Highest one bit of the given integer is = ");
        System.out.println(Integer.highestOneBit(a));
    }
}
```

**Output:** 

```
Number is = -9
Highest one bit of the given integer is = -2147483648
```

**程序 3:** 为十进制值。
**注意:**当十进制值因为类型不兼容而作为参数传递时，它会返回一条错误消息。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// Java.lang.Integer.highestOneBit() Method
import java.lang.*;

public class HighestOneBit {

    public static void main(String[] args)
    {

        int a = 84.22;
        System.out.println("Number is = " + a);

        // decimal value 84.22 is passed here
        System.out.print("Highest one bit of the given integer is = ");
        System.out.println(Integer.highestOneBit(a));
    }
}
```

**Output:** 

```
prog.java:9: error: incompatible types: possible lossy conversion from double to int
    int a = 84.22;
            ^
1 error
```

**程序 4:** 为字符串。
**注意:**当字符串因为类型不兼容而作为参数传递时，它会返回一条错误消息。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// Java.lang.Integer.highestOneBit() Method
import java.lang.*;

public class HighestOneBit {

    public static void main(String[] args)
    {

        int a = "34";
        System.out.println("Number is = " + a);

        // decimal value 84.22 is passed here
        System.out.print("Highest one bit of the given integer is = ");
        System.out.println(Integer.highestOneBit(a));
    }
}
```

**Output:** 

```
prog.java:9: error: incompatible types: String cannot be converted to int
    int a = "34";
            ^
1 error
```