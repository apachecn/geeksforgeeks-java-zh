# Java.lang.Long.valueOf()方法示例

> 原文:[https://www . geesforgeks . org/Java-lang-long-value of-method-with-examples/](https://www.geeksforgeeks.org/java-lang-long-valueof-method-with-examples/)

**Java.lang.Long.valueOf()** 是 lang 类的 Java 中的一个内置方法，当用第二个参数中给出的基数解析时，返回一个 Long 对象，该对象保存从指定字符串 S 中提取的值。第一个参数被解释为表示由第二个参数指定的基数中的带符号长，就像这些参数是给 parseLong(java.lang.String，int)方法的一样。它返回一个 Long 对象的结果，该对象表示由字符串指定的长值。

**语法:**

```
public static Long valueOf(String s, int radix) throws NumberFormatException
```

**参数:**该方法接受两个强制参数:

*   *S:* 这是指要解析的字符串。
*   *基数:*这是指用于解释字符串 s 的基数

**返回类型:**内置方法返回一个 Long 对象，该对象以指定的基数保存字符串参数表示的值。

**错误和异常:**

*   **NumberFormatException:** 如果数字不包含可解析的长整型，程序将返回。

下面的程序说明了 Java.lang.Long.valueOf()方法。

**程序 1:**

```
// Java program to demonstrate
// the java.lang.Long.valueOf() method
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        Long l = new Long(10);
        String str = "45325";

        // returns a Long instance representing 
        // the specified string with radix 10
        System.out.println("Long instance Value = " 
                               + l.valueOf(str, 10));
    }
}
```

输出:

```
Long instance Value = 45325

```

**程序 2:**

```
// Java program to demonstrate
// of java.lang.Long.valueOf() method
// NumberFormatException
import java.lang.Math;

class Gfg1 {

    // driver code
    public static void main(String args[])
    {
        Long l = new Long(10);

        // not a parsable long
        String str = "gopal";

        // returns a Long instance representing 
        // the specified string with radix 10
        System.out.println("Long instance Value = " 
                               + l.valueOf(str, 10));
    }
}
```

输出:

```
Exception in thread "main" java.lang.NumberFormatException: For input string: "gopal"
    at java.lang.NumberFormatException.forInputString(NumberFormatException.java:65)
    at java.lang.Long.parseLong(Long.java:589)
    at java.lang.Long.valueOf(Long.java:776)
    at Gfg1.main(File.java:15)

```