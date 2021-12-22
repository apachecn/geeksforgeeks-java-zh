# Java 中的整数 signum()方法

> 原文:[https://www . geesforgeks . org/integer-signum-in-method-Java/](https://www.geeksforgeeks.org/integer-signum-method-in-java/)

符号函数是一种提取实数符号的奇数数学函数。符号函数也称为符号函数。java.lang 的 Integer.signum()方法返回指定整数值的 [signum 函数](https://en.wikipedia.org/wiki/Sign_function)。对于正值、负值和零，该方法分别返回 1、-1 和 0。

**语法:**

```java
public static int signum(*int a*)
```

**参数:**该方法取一个整数类型的参数 *a* ，对其进行运算。

**返回值:**该方法返回指定整数值的 signum 函数。如果指定值为负值，则返回-1；如果指定值为零，则返回 0；如果指定值为正值，则返回 1。

**示例:**

```java
Consider an integer a = 27
Since 27 is a positive int signum will return= 1

Consider another integer a = -61
Since -61 is a negative int signum will return= -1

Consider the integer value *a* = 0
For a zero signum, it will return = 0 
```

下面的程序说明了方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// Java.lang.Integer.signum() Method
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    // It will return 1 as  the int value is greater than 1
    System.out.println(Integer.signum(1726));

    // It will return -1 as  the int value is less than 1
    System.out.println(Integer.signum(-13));

    // It will returns 0 as int value is equal to 0
    System.out.println(Integer.signum(0));
}
}
```

**Output:** 

```java
1
-1
0
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// Java.lang.Integer.signum() Method
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    // It will return 1 as  the int value is greater than 1
    System.out.println(Integer.signum(-1726));

    // It will return -1 as  the int value is less than 1
    System.out.println(Integer.signum(13));

    // It will returns 0 as int value is equal to 0
    System.out.println(Integer.signum(0));
}
}
```

**Output:** 

```java
-1
1
0
```

**程序 3:** 为十进制值和字符串。
**注意:**当十进制值和字符串作为参数传递时，它会返回一条错误消息。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// Java.lang.Integer.signum() Method
import java.lang.*;

public class Geeks {

public static void main(String[] args) {

    //returns compile time error as passed argument is a decimal value
    System.out.println(Integer.signum(3.81));

    //returns compile time error as passed argument is a string
    System.out.println(Integer.signum("77"));

}
}
```

**Output:** 

```java
prog.java:10: error: incompatible types: possible lossy conversion from double to int
    System.out.println(Integer.signum(3.81));
                                      ^
prog.java:14: error: incompatible types: String cannot be converted to int
    System.out.println(Integer.signum("77"));
                                      ^
Note: Some messages have been simplified; recompile with -Xdiags:verbose to get full output
2 errors
```