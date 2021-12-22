# 如何用 Java 打印竞技编程中的快速输出？

> 原文:[https://www . geesforgeks . org/how-print-fast-output-in-competitive-programming-use-Java/](https://www.geeksforgeeks.org/how-to-print-fast-output-in-competitive-programming-using-java/)

在竞争性编程中，大多数学生使用 C++作为他们的主要语言，因为它比其他语言(例如 Java、Python)更快，但是对于使用 Java 作为他/她的主要语言的学生/专业人员来说，从输入流中获取输入并打印快速输出是在竞争性平台(例如 CodeChef、CodeForces、Spoj 等)上进行竞赛时面临的主要困难。

*在本文中，定义了使用 Java 打印 O/P 的最快方法(主要在竞争性编程中)。*

[**BufferedWriter 类:**](https://www.geeksforgeeks.org/io-bufferedwriter-class-methods-java/) 它将文本写入字符输出流，缓冲字符以提供单个字符、数组和字符串的高效写入。它使表演变得很快。

> BufferedWriter 输出= new BufferedWriter(new OutputStreamWriter(system . out))；

**缓冲写入器的方法:**

*   **write():** 将单个字符写入写入程序的内部缓冲区。
*   **write(char[]数组):**将指定数组中的字符写入 writer。
*   **写入(字符串数据):**将指定的字符串写入写入器。
*   **flush():** 用于清除内部缓冲区。
*   **close():** 用于关闭缓冲写入器。

下面是问题陈述的实现:

T3】JavaT5

```
// Print fast Output in Competitive Programming using JAVA
import java.io.*;

class GFG {
    public static void main(String[] args) throws Exception
    {
        String[] gfg = { "Geeks", "For", "Geeks" };

        BufferedWriter output = new BufferedWriter(
            new OutputStreamWriter(System.out));

        for (int i = 0; i < gfg.length; i++) {
            output.write(gfg[i] + "\n");
        }

        output.flush();
    }
}
```

T6T8**输出**T1