# Java 中的文字

> 原文:[https://www.geeksforgeeks.org/literals-in-java/](https://www.geeksforgeeks.org/literals-in-java/)

**文字:**任何可以赋给变量的常量值都称为文字/常量。

简单来说，Java 中的文字是布尔、数字、字符或字符串数据的综合表示。它是在程序中表达特定值的一种媒介，例如名为' '/count 的整数变量在下面的语句中被赋予一个整数值。

```
// Here 100 is a constant/literal.
int x = 100; 
```

### 整数

对于整型数据类型(字节、短整型、整型、长整型)，我们可以用 4 种方式指定文字:-

**十进制文字(基数 10):** 在这种形式中，允许的数字是 0-9。

```
int x = 101;
```

**八进制文字(基数 8):** 在这种形式中，允许的数字是 0-7。

```
// The octal number should be prefix with 0.
int x = 0146; 
```

**六位十进制文字(Base 16):** 在这种形式中，允许的数字是 0-9，字符是 a-f，我们可以同时使用大写和小写字符，因为我们知道 java 是一种区分大小写的编程语言，但是这里 java 不区分大小写。

```
// The hexa-decimal number should be prefix
// with 0X or 0x.
int x = 0X123Face; 
```

**二进制文字:**从 1.7 开始，我们甚至可以用二进制形式指定文字值，允许的数字是 0 和 1。文字值应该以 0b 或 0B 为前缀。

```
int x = 0b1111;
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// application of Integer literals

public class Test {
    public static void main(String[] args)
    {
          // decimal-form literal
        int a = 101;
          // octal-form literal
        int b = 0100;
        // Hexa-decimal form literal
        int c = 0xFace;
          // Binary literal
        int d = 0b1111;

        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
        System.out.println(d);
    }
}
```

**Output**

```
101
64
64206
15
```

> **注意:**默认情况下，每个文字都是 int 类型，我们可以通过以 l 或 l 为后缀来明确指定为 long 类型，没有办法明确指定字节和短文字，但是我们可以间接指定。每当我们给字节变量赋值时，如果该值在字节范围内，编译器会自动将其视为字节文字。

### 浮点文字

对于浮点数据类型，我们只能以十进制形式指定文字，不能以八进制和十六进制形式指定。

**十进制文字(基数 10):** 在这种形式中，允许的数字是 0-9。

```
double d = 123.456;
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the 
// application of floating-point literals

public class Test {
    public static void main(String[] args)
    {
          // decimal-form literal
        float a = 101.230;
          // It also acts as decimal literal
        float b = 0123.222;
          // Hexa-decimal form (error)
        float c = 0x123.222;

        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
    }
}
```

**输出**

```
101.230
123.222
Error: malformed floating point literal
```

> **注意:**默认情况下，每个浮点文字都是双精度类型，因此我们不能直接赋值给浮点变量。但是我们可以通过以 f 或 f 为后缀将浮点文字指定为浮点类型。我们可以通过以 d 或 d 为后缀将浮点文字显式指定为双精度类型。当然，这种约定不是必需的。

### 字符文字

对于 char 数据类型，我们可以用 4 种方式指定文字:

**单引号:**我们可以将字符数据类型的文字指定为单引号中的单个字符。

```
char ch = 'a';
```

**将字符文字指定为整数文字:**我们可以将字符文字指定为整数文字，它表示字符的 Unicode 值，该整数文字可以以十进制、八进制和十六进制形式指定。但是允许的范围是 0 到 65535。

```
char ch = 062;
```

**Unicode 表示法:**我们可以在 Unicode 表示法“\ uxxxx”中指定字符文字。这里 xxxx 代表 4 个十六进制数。

```
char ch = '\u0061';// Here /u0061 represent a.
```

**转义序列:**每个转义字符都可以被指定为字符。

```
char ch = '\n';
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// application of char literals

public class Test {
    public static void main(String[] args)
    {
          // single character literl within single quote
        char ch = 'a';
          // It is an Integer literal with octal form
        char b = 0789;
          // Unicode representation
        char c = '\u0061';

        System.out.println(ch);
        System.out.println(b);
        System.out.println(c);

        // Escape character literal
        System.out.println("\"  is a symbol");
    }
}
```

**输出**

```
a
error:Integer number too large
a
"  is a symbol
```

### 字符串文字

双引号内的任何字符序列都被视为字符串。

```
String s = "Hello";
```

字符串不能包含非转义换行符或换行符。但是，Java 编译器将评估编译时表达式，因此下面的字符串表达式会生成一个包含三行文本的字符串:

```
Example:
String text = "This is a String literal\n"
            + "which spans not one and not two\n"
            + "but three lines of text.\n";
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// application of String literals

public class Test {
    public static void main(String[] args)
    {
        String s = "Hello";

        // If we assign without "" then it treats
        // as a variable and causes compiler error
        String s1 = Hello;

        System.out.println(s);
        System.out.println(s1);
    }
}
```

**输出**

```
Hello
error: cannot find symbol
symbol:   variable Hello
location: class Test
```

### 布尔文字

布尔文字只允许有两个值，即真和假。

```
boolean b = true;
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the
// application of boolean literals

public class Test {
    public static void main(String[] args)
    {
        boolean b = true;
        boolean c = false;
        boolean d = 0;
        boolean b = 1;

        System.out.println(b);
        System.out.println(c);
        System.out.println(d);
        System.out.println(e);
    }
}
```

**输出**

```
true
false
error: incompatible types: int cannot be converted to boolean
error: incompatible types: int cannot be converted to boolean
```

> **注意:**当我们执行串联操作时，括号中的值首先被串联。然后这些值从左到右串联起来。当我们在字符串连接操作中混合字符文字和整数时，我们应该小心，这种类型的操作被称为**混合模式操作**。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate the behaviour of
// char literals and integer literals when
// we are performing addition

public class Test {
    public static void main(String[] args)
    {
        // ASCII value of 0 is 48
        int first = '0';

        // ASCII value of 7 is 55
        int second = '7';
        System.out.println("Geeks!" + first +
                                '2' + second);
    }
}
```

**Output**

```
Geeks!48255
```

**说明:**每当我们在字符串和整数之间进行加法运算时，总的结果都会转换成字符串。上述程序评估通过以下方式完成:

```
"Geeks!" + first + '2' + second
"Geeks! " + 48 + '2' + 55
"Geeks!48" + '2' + 55
"Geeks!482" + 55
"Geeks!48255"
```

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。