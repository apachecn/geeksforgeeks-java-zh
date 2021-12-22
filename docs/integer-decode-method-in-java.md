# Java 中的整数解码()方法

> 原文:[https://www . geesforgeks . org/integer-decode-method-in-Java/](https://www.geeksforgeeks.org/integer-decode-method-in-java/)

经常看到(" ")中的任何整数也被认为是字符串，那么需要将其解码为整数。**Java . lang . Integer . decode()**方法的主要功能是将一个 String 解码成一个 Integer。该方法还接受十进制、十六进制和八进制数。

**语法:**

```
public static Integer decode(String str)
```

**参数:**该方法取 String 数据类型的一个参数 *str* ，引用需要解码的字符串。

**返回值:**该方法返回一个整数对象，该对象保存由字符串 *str* 表示的整数值。

**异常:**当字符串包含无法解析的整数时，该方法抛出*numberformateexception*。

**示例:**

```
Input: str_value = "50"
Output: 50

Input: str_value = "GFG"
Output: *NumberFormatException*
```

下面的程序说明了 java.lang.Integer.decode()方法。
**节目一:**

```
// Java program to demonstrate working
// of java.lang.Integer.decode() method
import java.lang.*;

public class Gfg {

    public static void main(String[] args)
    {

        Integer int1 = new Integer(22);
        // string here given the value of 65
        String nstr = "65";

        // Returns an Integer object holding the int value
        System.out.println("Actual Integral Number = "+
        int1.decode(nstr));
    }
}
```

**Output:**

```
Actual Integral Number = 65

```

**程序 2:** 当字符串值被传递时，抛出*数字格式异常*。

```
// Java program to demonstrate working
// of java.lang.Integer.decode() method
import java.lang.*;

public class Gfg {

    public static void main(String[] args)
    {

        Integer int1 = new Integer(22);

        // String here passed as "geeksforgeeks"
        String nstr = "geeksforgeeks";

        System.out.println("Actual Integral Number = ");
        System.out.println(int1.decode(nstr));
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.NumberFormatException: For input string: "geeksforgeeks"
    at java.lang.NumberFormatException.forInputString(NumberFormatException.java:65)
    at java.lang.Integer.parseInt(Integer.java:580)
    at java.lang.Integer.valueOf(Integer.java:740)
    at java.lang.Integer.decode(Integer.java:1197)
    at Gfg.main(Gfg.java:15)

```