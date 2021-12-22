# 字符串的编译时间与运行时间分辨率

> 原文:[https://www . geeksforgeeks . org/compiletime-vs-runtime-resolution-of-strings/](https://www.geeksforgeeks.org/compiletime-vs-runtime-resolution-of-strings/)

<u>**字符串的编译时解析**</u> :

当字符串在[字符串文字](https://www.geeksforgeeks.org/literals-in-java/)和“+”运算符的帮助下被创建时，它们在编译时被连接在一起。这被称为字符串的编译时解析。编译器消除了串联运算符并优化了字符串。

**示例:**

考虑下面的代码:

```
String str = "Geeks "
             + "for"
             + "Geeks";
```

上面的代码由编译器通过字符串的编译时解析进行优化，如下所示:

```
String str = "GeeksforGeeks";
```

<u>**字符串的运行时解析**</u> :

当字符串在[字符串文字](https://www.geeksforgeeks.org/literals-in-java/)以及变量和“+”运算符的帮助下创建时，它们仅在运行时连接在一起，因为变量的值无法预先预测。这被称为字符串的运行时解析。

**示例:**

考虑下面的代码:

```
String str = "Geeks " + var + "Geeks";
```

由于变量“var”的值未知，编译器无法在编译时优化上述代码。因此，字符串的运行时解析发生在这里。

**不同场景，识别分辨率类型:**

1.  Suppose the String is defined using a StringBuffer:

    ```
    String str = (new StringBuffer())
                     .append("Geeks")
                     .append("for")
                     .append("Geeks")
                     .toString();
    ```

    **字符串解析类型:** <u>字符串的运行时解析</u>

    这里编译器不能在编译时解析，因为对象创建是一个运行时活动。因此，上面的字符串将在运行时解析。

2.  Suppose the String is defined using a StringBuffer:

    ```
    String str = "Geeks"
                 + " "
                 + "for"
                 + " "
                 + "Geeks";
    ```

    **字符串解析类型:** <u>字符串的编译时解析</u>

    这里编译器可以在编译时解析，因为给定的字符串是字符串文字。因此，上述字符串将在编译时解析。

3.  Suppose the String is defined in a return statement:

    ```
    public static String func(String var)
    {
        return "Geeks" + var + "Geeks";
    }
    ```

    **字符串解析类型:** <u>字符串的运行时解析</u>

    这里，编译器无法在编译时解析，因为变量“var”的值是运行时活动。因此，上面的字符串将在运行时解析。