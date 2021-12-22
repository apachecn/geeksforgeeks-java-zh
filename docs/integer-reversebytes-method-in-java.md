# Java 中的整数反转字节()方法

> 原文:[https://www . geesforgeks . org/integer-reverse bytes-method-in-Java/](https://www.geeksforgeeks.org/integer-reversebytes-method-in-java/)

Java . lang . integer . reverse bytes(int a)是一个内置方法，它返回通过反转指定 int 值的二进制补码表示中*字节*的顺序而获得的值。

**语法:**

```java
public static int reverseBytes(*int a*)
```

**参数:**该方法取一个整数类型的参数 *a* ，其字节将被反转。

**返回值:**该方法将返回通过反转指定 int 值中的字节而获得的值。

**示例:**

```java
Input: 75
Output: 1258291200
Explanation:
Consider an integer a = 75 
Binary Representation = 1001011
Number of one bit = 4 
After reversing the bytes we get = 1258291200

Input: -43
Output: -704643073

```

下面的程序说明了 java.lang.Integer.reverseBytes()方法:
**程序 1:** 为正数。

```java
// Java program to illustrate the
// Java.lang.Integer.reverseBytes() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = 61;
        System.out.println(" Integral Number = " + a);

        // It will return the value obtained by reversing the bytes in the
        // specified int value
        System.out.println("After reversing the bytes we get = " + 
        Integer.reverseBytes(a));
    }
}
```

**Output:**

```java
Integral Number = 61
After reversing the bytes we get = 1023410176

```

**程序 2:** 为负数。

```java
// Java program to illustrate the
// Java.lang.Integer.reverseBytes() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = -43;
        System.out.println(" Integral Number = " + a);

        // It will return the value obtained by reversing the bytes in the
        // specified int value
        System.out.println("After reversing the bytes we get = " + 
        Integer.reverseBytes(a));
    }
}
```

**Output:**

```java
Integral Number = -43
After reversing the bytes we get = -704643073

```

**程序 3:** 为十进制值和字符串。
**注意:**当十进制值和字符串作为参数传递时，它会返回一条错误消息。

```java
// Java program to illustrate the
// Java.lang.Integer.reverseBytes() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = 37.81;
        System.out.println(" Integral Number = " + a);
        // It will return the value obtained by reversing the bytes in the
        // specified int value
        System.out.println("After reversing the bytes we get = " + 
        Integer.reverseBytes(a));

        a = "81"; // compile time error will be generated
        System.out.println(" Integral Number = " + a);
        System.out.println("After reversing the bytes we get = " + 
        Integer.reverseBytes(a));
    }
}
```

**Output:**

```java
prog.java:9: error: incompatible types: possible lossy conversion from double to int
    int a = 37.81;
            ^
prog.java:18: error: incompatible types: String cannot be converted to int
    a = "81";
        ^
2 errors

```