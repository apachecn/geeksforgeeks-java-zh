# 在 Java 中使用正则表达式从字符串中提取每个单词

> 原文:[https://www.geeksforgeeks.org/extracting-word-string-java/](https://www.geeksforgeeks.org/extracting-word-string-java/)

给定一个字符串，从中提取单词。“单词”被定义为字母字符的连续串，即任何大写或小写字符 a-z 或 A-Z

示例:

```
Input : Funny?? are not you?
Output : Funny
         are
         not
         you

Input : Geeks for geeks?? 
Output : Geeks
         for
         geeks

```

在这篇文章中，我们讨论了 C++的一个解决方案:[从给定字符串中提取单词的程序](https://www.geeksforgeeks.org/program-extract-words-given-string/)

在这些文章中，我们还讨论了 java 的基本方法:[使用 Java 计算文本文件中的行数、字数、字符数和段落数](https://www.geeksforgeeks.org/counting-number-lines-words-characters-paragraphs-text-file-using-java/)和[使用 Regex](https://www.geeksforgeeks.org/print-first-letter-word-string-using-regex/) 打印单词中的第一个字母。

在这篇文章中，我们将讨论[正则表达式](https://www.geeksforgeeks.org/regular-expressions-in-java/)的方法。这种方法在时间复杂度方面是最好的，也适用于大型输入文件。下面是任何单词的正则表达式。

```
[a-zA-Z]+

```

```
// Java program to demonstrate extracting words
// from string using Regex

import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class Test 
{
    public static void main(String[] args) 
    {
        String s1 = "Geeks for Geeks";
        String s2 = "A Computer Science Portal for Geeks";

        Pattern p = Pattern.compile("[a-zA-Z]+");

        Matcher m1 = p.matcher(s1);
        Matcher m2 = p.matcher(s2);

        System.out.println("Words from string \"" + s1 + "\" : ");
        while (m1.find()) {
            System.out.println(m1.group());
        }

        System.out.println("Words from string \"" + s2 + "\" : ");
        while (m2.find()) {
            System.out.println(m2.group());
        }

    }
}
```

输出:

```
Words from string "Geeks for Geeks" : 
Geeks
for
Geeks
Words from string "A Computer Science Portal for Geeks" : 
A
Computer
Science
Portal
for
Geeks

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。