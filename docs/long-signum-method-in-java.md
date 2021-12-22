# Java 中的 Long signum()方法

> 原文:[https://www.geeksforgeeks.org/long-signum-method-in-java/](https://www.geeksforgeeks.org/long-signum-method-in-java/)

符号函数也称为符号函数，是一种提取实数符号的奇数数学函数。
Java . lang . long . signum()方法用于获取指定长值的 signum 函数。对于正值、负值和零，该方法分别返回 1、-1 和 0。

**语法:**

```
public static int signum(*long num*)
```

**参数:**该方法接受一个长型参数*数*，在其上执行信号操作。

**返回值:**该方法返回指定长值的 signum 函数。如果指定值为:

*   负，则该方法返回-1。
*   零，则该方法返回 0。
*   正，则该方法返回 1。

**示例:**

```
Input: (Long) 2731766
Output: 1

Input: (Long) -233611 
Output: -1

Input: (Long) 0
Output: 0

```

下面的程序说明了 Java.lang.Long.signum()方法:
**程序 1:**

```
// Java program to illustrate the
// Java.lang.Long.signum() Method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        // It will return 1 as long value is greater than 1
        System.out.println(Long.signum(36565531));

        // It will return -1 as long value is less than 1
        System.out.println(Long.signum(-628127));

        // Returns 0 as long value is equal to 0
        System.out.println(Long.signum(0));
    }
}
```

**Output:**

```
1
-1
0

```

**程序 2:** 为十进制值和字符串。

```
// Java program to illustrate the
// Java.lang.Long.signum() Method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        // It will return compile time error
        System.out.println(Long.signum(36565.531));

        // It will return compile time error
        System.out.println(Long.signum("628127"));
    }
}
```

**Output:**

```

prog.java:10: error: incompatible types: possible lossy conversion from double to long
    System.out.println(Long.signum(36565.531));
                                   ^
prog.java:13: error: incompatible types: String cannot be converted to long
    System.out.println(Long.signum("628127"));
                                   ^
Note: Some messages have been simplified; recompile with -Xdiags:verbose to get full output
2 errors

```