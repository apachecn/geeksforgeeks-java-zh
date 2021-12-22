# Java 中整数到字符串转换的不同方式

> 原文:[https://www . geesforgeks . org/Java 中整数到字符串转换的不同方式/](https://www.geeksforgeeks.org/different-ways-for-integer-to-string-conversions-in-java/)

*   **使用**转换[整数. toString(int)](https://www.geeksforgeeks.org/integer-tostring-in-java/)
    整数类有一个静态方法，返回一个代表指定 int 参数的 String 对象。
    **语法:**

```
public static String toString(int i)
```

参数 *i* 被转换并作为字符串实例返回。如果数字是负数，符号将被保留。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int a = 1234;
    int b = -1234;
    String str1 = Integer.toString(a);
    String str2 = Integer.toString(b);
    System.out.println("String str1 = " + str1);
    System.out.println("String str2 = " + str2);
  }
}
```

**输出:**

```
String str1 = 1234
String str2 = -1234
```

*   **转换使用** [字符串. value of(int)](https://www.geeksforgeeks.org/data-conversion-using-valueof-method-java/)
    T5】示例:

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int c = 1234;
    String str3 = String.valueOf(c);
    System.out.println("String str3 = " + str3);
  }
}
```

或者

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    String str3 = String.valueOf(1234);
    System.out.println("String str3 = " + str3);
  }
}
```

**输出:**

```
String str3 = 1234
```

*   **使用整数(int)进行转换。**
    这个方法使用整数类的一个实例来调用它的 toString()方法。
    **例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int d = 1234;
    Integer obj = new Integer(d);
    String str4 = obj.toString();
    System.out.println("String str4 = " + str4);
  }
}
```

或者

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int d = 1234;
    String str4 = new Integer(d).toString();
    System.out.println("String str4 = " + str4);
  }
}
```

或者

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    String str4 = new Integer(1234).toString();
    System.out.println("String str4 = " + str4);
  }
}
```

**输出:**

```
String str4 = 1234
```

如果变量是基元类型(int)，最好使用 Integer.toString(int)或 String.valueOf(int)。但是，如果您的变量已经是 Integer(原语类型 int 的包装类)的实例，那么最好只调用它的 toString()方法，如上所示。
**该方法效率不高，因为在执行转换之前创建了整数类的** **实例。**

*   类是一个将数字格式化为字符串的类。
    **例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.text.DecimalFormat;
class GfG
{
  public static void main(String args[])
  {
    int e = 12345;
    DecimalFormat df = new DecimalFormat("#");
    String str5 = df.format(e);
    System.out.println(str5);
  }
}
```

**输出:**

```
String str5 = 12345
```

或者

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.text.DecimalFormat;
class GfG
{
  public static void main(String args[])
  {
    int e = 12345;
    DecimalFormat df = new DecimalFormat("#,###");
    String Str5 = df.format(e);
    System.out.println(Str5);
  }
}
```

**输出:**

```
String str5 = 12,345
```

使用此方法，您可以指定小数位数和逗号分隔符以提高可读性。

*   **使用** [字符串填充器](https://www.geeksforgeeks.org/stringbuffer-class-in-java/) **或** [字符串构建器](https://www.geeksforgeeks.org/stringbuilder-class-in-java-with-examples/)
    字符串填充器是一个用于将多个值连接成字符串的类。StringBuilder 的工作原理类似，但不像 StringBuffer 那样是线程安全的。
    **StringBuffer 示例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int f = 1234;
    StringBuffer sb = new StringBuffer();
    sb.append(f);
    String str6 = sb.toString();
    System.out.println("String str6 = " + str6);
  }
}
```

或者

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    String str6 = new StringBuffer().append(1234).toString();
    System.out.println("String str6 = " + str6);
  }
}
```

**输出:**

```
String str6 = 1234
```

*   **字符串构建器示例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int g = 1234;
    StringBuilder sb = new StringBuilder();
    sb.append(g);
    String str7 = sb.toString();
    System.out.println("String str7 = " + str7);
  }
}
```

或者

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    String str7 = new StringBuilder().append(1234).toString();
    System.out.println("String str7 = " + str7);
  }
}
```

**输出:**

```
String str7 = 1234
```

*   **用特殊基数**转换
    以上所有例子都使用基数(基数)10。以下是转换为二进制、八进制和十六进制的方便方法。还支持任意自定义号码系统。
    **示例:**
    **二进制**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int h = 255;
    String binaryString = Integer.toBinaryString(h);
    System.out.println(binaryString);
  }
}
```

**输出:**

```
11111111
```

11111111 是数字 255 的二进制表示。

**八进制**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int i = 255;
    String octalString = Integer.toOctalString(i);
    System.out.println(octalString);
  }
}
```

**输出:**

```
377
```

377 是数字 255 的八进制表示。

**十六进制**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int j = 255;
    String hexString = Integer.toHexString(j);
    System.out.println(hexString);
  }
}
```

**输出:**

```
ff
```

**ff** 是数字 255 的十六进制表示。

**自定义基数/基数**
将整数转换为字符串时，可以使用任何其他自定义基数/基数。
以下示例使用基数为 7 的数字系统。

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG
{
  public static void main(String args[])
  {
    int k = 255;
    String customString = Integer.toString(k, 7);
    System.out.println(customString);
  }
}
```

**输出:**

```
513
```

513 是数字 255 在 7 进制中的表示。

**使用空字符串串联:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
class GfG {
    public static void main(String args[])
    {
        int a = 1234;
        int b = -1234;
        String str1 = "" + a;
        String str2 = "" + b;
        System.out.println("String str1 = " + str1);
        System.out.println("String str2 = " + str2);
    }
}
```

**Output**

```
String str1 = 1234
String str2 = -1234

```

本文由**阿米特·坎德尔瓦尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。