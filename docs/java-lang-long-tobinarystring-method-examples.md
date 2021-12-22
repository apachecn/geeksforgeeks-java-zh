# 爪哇郎。Long.toBinaryString()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-lang-long-tobinarystring-method-examples/](https://www.geeksforgeeks.org/java-lang-long-tobinarystring-method-examples/)

Java . lang . long . tobinarystring()方法将长参数的字符串表示形式作为基数为 2 的无符号整数返回。它接受 Long 数据类型的参数，并返回相应的二进制字符串。

**语法:**

```java
public static String toBinaryString(long num)

Parameters : The function accepts a single mandatory parameter: 
num - This parameter specifies the number to be converted to binary string. 
It is of Long data-type.

```

**返回值:**该函数返回由二进制(基数为 2)中的参数表示的无符号 Long 值的字符串表示形式。

示例:

```java
Input : 10 
Output : 1010 

Input : 9
Output : 1001 

```

**程序 1 :** 下面的程序演示了功能的工作。

```java
// Java program to demonstrate
// of java.lang.Long.toBinaryString() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        long l = 10;
        // returns the string representation of the unsigned long value
        // represented by the argument in binary (base 2)
        System.out.println("Binary is " + Long.toBinaryString(l));

        l = 20987752;
        System.out.println("Binary is " + Long.toBinaryString(l));
    }
}
```

输出:

```java
Binary is 1010
Binary is 1010000000011111101101000

```

**程序二**:下面的程序演示了负数通过时的工作功能。

```java
// Java program to demonstrate overflow
// of java.lang.Long.toBinaryString() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        // conversion of a negative number to Binary
        long l = -13;
        System.out.println("Binary is " + Long.toBinaryString(l));
    }
}
```

输出:

```java
Binary is 1111111111111111111111111111111111111111111111111111111111110011

```

**错误和异常:**每当十进制数或字符串作为参数传递时，它都会返回一条错误消息，上面写着**“不兼容的类型”。**

**程序 3:** 下面的程序演示了当一个字符串数字被传递时的工作函数。

```java
// Java program to demonstrate overflow
// of java.lang.Long.toBinaryString() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        // error message thrown when a string is passed
        System.out.println("Binary is " + Long.toBinaryString("10"));
    }
}
```

输出:

```java
prog.java:12: error: incompatible types: String cannot be converted to long
    System.out.println("Binary is " + Long.toBinaryString("10"));
```

**程序 4:** 下面的程序演示了传递小数时的工作功能。

```java
// Java program to demonstrate overflow
// of java.lang.Long.toBinaryString() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {

        // error message thrown when a decimal is passed
        System.out.println("Binary is " + Long.toBinaryString(10.25));
    }
}
```

输出:

```java
prog.java:12: error: incompatible types: possible lossy conversion from double to long
    System.out.println("Binary is " + Long.toBinaryString(10.25));
```