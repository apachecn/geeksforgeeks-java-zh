# Java 中的可执行注释

> 原文:[https://www.geeksforgeeks.org/executable-comments-java/](https://www.geeksforgeeks.org/executable-comments-java/)

注释是一种不被编译器或解释器执行的语句，但是在编译器中对程序进行词法转换之前，程序的内容被编码成 ASCII 码以使处理更容易。考虑这个计划:

```
class Main{

    public static void main(String[] args) {
        // The comment below is magic..
        // \u000d System.out.println("Geek Comment Executed!");
    }
}
```

该代码将被成功执行和编译以产生输出。
**输出**

```
Geek Comment Executed!

```

这成功地产生了这个输出，因为在词法转换之前，java 编译器将 Unicode 字符\u 00d 解析为一个新行，并且程序被转换为:

```
class Main{

    public static void main(String[] args) {
        // The comment below is magic
        //
        System.out.println("Geek Comment Executed!");
    }
}
```

Unicode 字符将打印语句移到下一行，然后像普通的 java 程序一样执行。那么，问题就来了，为什么 Unicode 转义的翻译先于任何其他源代码处理？

1.Java 源代码可以用任何允许字符串、文字和注释中各种字符的编码来编写。
1。它使基于 ASCII 的工具的处理更加容易。
2。这保证了 java 平台的依赖性，即独立于支持的字符集。
3。这有助于用非拉丁语言记录代码。

能够在文件中的任何地方编写任何 Unicode 字符是一个很好的特性，事实上它会以如此微妙的方式干扰语义，这只是一个副作用。

让我们考虑一下这个 java 程序:

```
\u0070\u0075\u0062\u006c\u0069\u0063\u0020\u0020\u0020\u0020
\u0063\u006c\u0061\u0073\u0073\u0020\u0055\u0067\u006c\u0079
\u007b\u0070\u0075\u0062\u006c\u0069\u0063\u0020\u0020\u0020
\u0020\u0020\u0020\u0020\u0073\u0074\u0061\u0074\u0069\u0063
\u0076\u006f\u0069\u0064\u0020\u006d\u0061\u0069\u006e\u0028
\u0053\u0074\u0072\u0069\u006e\u0067\u005b\u005d\u0020\u0020
\u0020\u0020\u0020\u0020\u0061\u0072\u0067\u0073\u0029\u007b
\u0053\u0079\u0073\u0074\u0065\u006d\u002e\u006f\u0075\u0074
\u002e\u0070\u0072\u0069\u006e\u0074\u006c\u006e\u0028\u0020
\u0022\u0048\u0065\u006c\u006c\u006f\u0020\u0077\u0022\u002b
\u0022\u006f\u0072\u006c\u0064\u0022\u0029\u003b\u007d\u007d
```

输出:

```
Hello World

```

这个 unicode 程序被转换成它的代表值来产生“Hello World”
**参考**–
[https://stackoverflow . com/questions/30727515/为什么-执行-带有某些 unicode 字符的 Java-code-in-comments-是允许的？简讯=1 & nlcode=222379%7C1266](https://stackoverflow.com/questions/30727515/why-is-executing-java-code-in-comments-with-certain-unicode-characters-allowed?newsletter=1&nlcode=222379%7C1266)