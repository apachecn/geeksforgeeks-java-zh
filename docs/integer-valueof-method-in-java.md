# Java 中的整数值()方法

> 原文:[https://www . geesforgeks . org/integer-value of-method-in-Java/](https://www.geeksforgeeks.org/integer-valueof-method-in-java/)

1.**Java . lang . Integer . value of(*****int a*****)**是一个内置方法，用于返回表示指定 int 值 *a* 的整数实例。

**语法:**

```
public static Integer valueOf(*int a*)
```

**参数:**该方法接受一个整数类型的参数 *a* ,表示其整数实例将被返回的参数。

**返回值:**该方法返回一个代表 *a* 的整数实例。

**示例:**

```
Input: a = 65
Output: 65

Input: a = -985
Output: -985
```

下面的程序说明了 java.lang.Integer.valueOf(int a)方法。

**程序 1:** 为正数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// java.lang.Integer.valueOf(int a)
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        Integer obj = new Integer(10);

        // Returns an Integer instance  
        // representing the specified int value
        System.out.println("Output Value = " + 
                            obj.valueOf(85));
    }
}
```

**Output:**

```
Output Value = 85
```

**程序 2:** 为负数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// java.lang.Integer.valueOf(int a)
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        Integer obj = new Integer(10);

        // It will return a Integer instance 
        // representing the specified int value
        System.out.println("Output Value = " + 
                            obj.valueOf(-9185));
    }
}
```

**Output:**

```
Output Value = -9185
```

2.**Java . lang . Integer . value of(*****String str*****)**是一个内置方法，用于返回一个 Integer 对象，保存指定字符串 *str* 的值。

**语法:**

```
public static Integer valueOf(*String str*)
```

**参数:**该方法接受待解析的字符串类型的单个参数*字符串*。

**返回值:**该方法返回一个整数对象，该对象保存由字符串参数表示的值。

**示例:**

```
Input: str = "65"
Output: 65

Input: str = "-452"
Output: 452
```

下面的程序说明了 java.lang.Integer.valueOf(字符串)方法:

**程序 1:** 为正数。

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// java.lang.Integer.valueOf(String str)
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        Integer obj = new Integer(8);

        String str = "424";
        // It will return  a Integer instance
        // representing  the specified string
        System.out.println("Integer Value = " + 
                            obj.valueOf(str));
    }
}
```

**Output:**

```
Integer Value = 424
```

**程序 2:** 为负数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// java.lang.Integer.valueOf(String str)
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        Integer obj = new Integer(8);

        String str = "-6156";
        // It will return  a Integer instance
        // representing the specified string
        System.out.println("Output Value = " + 
                            obj.valueOf(str));
    }
}
```

**Output:**

```
Output Value = -6156
```

3.**Java . lang . Integer . value of(*****String s，int radix*** **)** 是一个内置的方法，它返回一个 Integer 对象，当用第二个参数给出的基进行解析时，保存从指定字符串中提取的值。

**语法:**

```
public static Integer valueOf(String str, int base)
```

**参数:**该方法接受两个参数:

*   *字符串*:这是要解析的字符串类型。
*   *基数*这是整数类型，指的是用于解释*字符串*的基数。

**返回值:**该方法返回一个整数对象，该对象保存由指定基数或基数的字符串参数表示的值。

**示例:**

```
Input: str = "1101"
       base = 2
Output: 13

Input: str = "101"
       base = 4
Output: 17
```

下面的程序说明了 java.lang.Integer.valueOf(字符串，int base)方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// java.lang.Integer.valueOf(String str, int base)
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {
        // Base = 2
        Integer val1 = Integer.valueOf("1010", 8);
        System.out.println(val1);

        // Base = 16
        Integer val2 = Integer.valueOf("1011", 16);
        System.out.println(val2);

        // Base = 2
        Integer val3 = Integer.valueOf("1010", 2);
        System.out.println(val3);

        // Base = 10
        Integer val4 = Integer.valueOf("1021", 10);
        System.out.println(val4);
    }
}
```

**Output:**

```
520
4113
10
1021
```