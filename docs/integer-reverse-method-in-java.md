# Java 中的整数逆向()方法

> 原文:[https://www . geesforgeks . org/integer-reverse-method-in-Java/](https://www.geeksforgeeks.org/integer-reverse-method-in-java/)

java.lang.Integer.reverse()是 java 中的一个内置方法，用于返回指定 int 值的二进制补码表示形式中位的逆序。

**语法:**

```java
public static int reverse(*int a*)
```

**参数:**参数 *a* 是一个整数值，其位将被反转。

**返回值:**该方法返回通过反转指定 int 值中的位的顺序而获得的值。

**示例:**

```java
Input: 86
Output: 1778384896
Explanation:
Consider an integer a = 86
Binary Representation = 1010110
The number of one bit = 4 
After reversing it is = 1778384896

Input: 168
Output: 352321536

```

下面的程序说明了 java.lang.Integer.reverse()方法:
**程序 1:** 为正数。

```java
// Java program to illustrate the
// Java.lang.Integer.reverse() method
import java.lang.*;

public class geeks {

    public static void main(String[] args)
    {

        int a = 168;
        System.out.println("Number = " + a);

        // It returns the value obtained by reversing order of the bits
        System.out.println("By reversing we get = " + Integer.reverse(a));
    }
}
```

**Output:**

```java
Number = 168
By reversing we get = 352321536

```

**程序 2:** 为负数。

```java
// Java program to illustrate the
// Java.lang.Integer.reverse() method
import java.lang.*;

public class geeks {

    public static void main(String[] args)
    {

        int a = -72;
        System.out.println("Number = " + a);

        // It returns the value obtained by reversing order of the bits
        System.out.println("By reversing we get = " + Integer.reverse(a));
    }
}
```

**Output:**

```java
Number = -72
By reversing we get = 503316479

```

**程序 3:** 为十进制值和字符串。
**注意:**当十进制值或字符串作为参数传递时，它会抛出一条错误消息。

```java
// Java program to illustrate the
// Java.lang.Integer.reverse() method
import java.lang.*;

public class geeks {

    public static void main(String[] args)
    {

        int a = 37.9;
        System.out.println("Number = " + a);

        // It returns the value obtained by reversing order of the bits in
        // the specified int value
        System.out.println("By reversing we get = " + Integer.reverse(a));
        a = "21";
        System.out.println("Number = " + a);

        // It returns the value obtained by reversing order of the bits in
        // the specified int value
        System.out.println("By reversing we get = " + Integer.reverse(a));
    }
}
```

**Output:**

```java
prog.java:9: error: incompatible types: possible lossy conversion from double to int
    int a = 37.9;
            ^
prog.java:17: error: incompatible types: String cannot be converted to int
     a = "21";
         ^
2 errors

```