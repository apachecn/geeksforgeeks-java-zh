# 使用字符文字存储 Unicode 字符的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到存储-unicode-字符-使用字符文字/](https://www.geeksforgeeks.org/java-program-to-store-unicode-characters-using-character-literals/)

Unicode 字符是通用字符编码标准。它代表了不同的字符在不同的文档中的表现方式，如文本文件、网页等。Unicode 支持 4 个字节的字符。UTF-8 已经成为标准字符编码，它支持每个字符 4 个字节。还有其他不同的 Unicode 编码，如 UTF-16、UTF-8。java 中的字符文字是 java 中的常量字符。它们用单引号' A '，' A '，' 1 '，'表示！，'π'，' { content } ' 2019；,' '.可以存储字符文字的数据类型是 char。通过使用下面给出的三种方法:

**方法 1:为字符数据类型分配 Unicode。**

**示例:**

```
Input : a = '{content}apos;
Output: $

Input : a = '~' 
Output: ~
```

**进场:**

1.  创建一个字符变量。
2.  使用单引号将 Unicode 字符存储在变量中。
3.  打印变量

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Assigning Unicode to the char data types
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        char c1 = 'a';
        System.out.println(c1);
        char c2 = 'A';
        System.out.println(c2);
        char c3 = '1';
        System.out.println(c3);
        char c4 = '~';
        System.out.println(c4);
        char c5 = '{content}apos;;
        System.out.println(c5);
        char c6 = '/';
        System.out.println(c6);
        char c7 = 'π';
        System.out.println(c7);
    }
}
```

**Output**

```
a
A
1
~
$
/
?

```

**方法 2:为字符数据类型分配 Unicode 值**

**示例:**

```
Input : a = '\u0061'
Output: a

Input : a = '\u002F' 
Output: /
```

**进场:**

1.  创建一个字符变量。
2.  使用单引号将 Unicode 值存储在变量中。
3.  打印变量

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Assigning Unicode values to char data types
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        char c1 = '\u0061';
        System.out.println(c1);
        char c2 = '\u0041';
        System.out.println(c2);
        char c3 = '\u0031';
        System.out.println(c3);
        char c4 = '\u007E';
        System.out.println(c4);
        char c5 = '\u0024';
        System.out.println(c5);
        char c6 = '\u002F';
        System.out.println(c6);
        char c7 = '\u03C0';
        System.out.println(c7);
    }
}
```

**Output**

```
a
A
1
~
$
/
?

```

**方法 3:为字符数据类型分配 ASCII 值**

**示例:**

```
Input : a = 97
Output: a

Input : a = 49 
Output: 1
```

**进场:**

1.  创建一个字符变量。
2.  使用单引号将 ASCII 值存储在变量中。
3.  打印变量

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Assigning ASCII values to char data types
import java.io.*;
class GFG {
    public static void main(String[] args)
    {
        char c1 = 97;
        System.out.println(c1);
        char c2 = 65;
        System.out.println(c2);
        char c3 = 49;
        System.out.println(c3);
        char c4 = 126;
        System.out.println(c4);
        char c5 = 36;
        System.out.println(c5);
        char c6 = 47;
        System.out.println(c6);
    }
}
```

**Output**

```
a
A
1
~
$
/

```