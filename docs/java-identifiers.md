# Java 标识符

> 原文:[https://www.geeksforgeeks.org/java-identifiers/](https://www.geeksforgeeks.org/java-identifiers/)

在编程语言中，标识符用于识别目的。在 Java 中，标识符可以是类名、方法名、变量名或标签。例如:

```
public class Test
{
    public static void main(String[] args)
    {
        int a = 20;
    }
}

```

在上面的 java 代码中，我们有 5 个标识符，即:

*   **测试**:类名。
*   **主**:方法名称。
*   **字符串**:预定义类名。
*   **args** :变量名。
*   **a** :变量名。

**定义 Java 标识符的规则**

定义有效的 java 标识符有一定的规则。必须遵守这些规则，否则我们会得到编译时错误。这些规则也适用于其他语言，如 C、C++。

*   标识符唯一允许的字符是所有字母数字字符([ **A-Z** ]，[ **a-z** ，[ **0-9** )，' **$** '(美元符号)和' **_** '(下划线)。例如，“geek@”不是有效的 java 标识符，因为它包含“@”特殊字符。
*   标识符不应以数字(**【0-9】**)开头。例如，“123geeks”不是有效的 java 标识符。
*   Java 标识符**区分大小写**。
*   标识符的长度没有限制，但建议仅使用 4-15 个字母的最佳长度。
*   **保留** **字**不能作为标识符。例如“int while = 20”是无效语句，因为 while 是保留字。爪哇有 **53** 保留字。

**有效标识符示例:**

```
MyVariable
MYVARIABLE
myvariable
x
i
x1
i1
_myvariable
$myvariable
sum_of_array
geeks123

```

**无效标识符示例:**

```
My Variable  // contains a space
123geeks   // Begins with a digit
a+c // plus sign is not an alphanumeric character
variable-2 // hyphen is not an alphanumeric character
sum_&_difference // ampersand is not an alphanumeric character

```

**保留字**

任何编程语言都会保留一些单词来表示该语言定义的功能。这些词叫做保留词。它们可以简单地分为两部分:**关键词** (50)和**文字** (3)。关键词定义功能，文字定义值。在编译器体系结构的不同分析阶段(如词法、语法、语义)，符号表使用标识符。

**注意:**关键字 const 和 goto 是保留的，即使它们当前没有被使用。用最后一个关键字代替 const。一些像 [strictfp](https://www.geeksforgeeks.org/strictfp-keyword-java/) 这样的关键词包含在 Java 的更高版本中。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。