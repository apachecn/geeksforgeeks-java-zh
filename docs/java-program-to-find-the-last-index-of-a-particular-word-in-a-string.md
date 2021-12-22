# 查找字符串中特定单词的最后一个索引的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-program-to-find-字符串中特定单词的最后索引/](https://www.geeksforgeeks.org/java-program-to-find-the-last-index-of-a-particular-word-in-a-string/)

从一个给定的字符串中找出一个字符或字符串的最后一次出现，在这个字符串中搜索子字符串或字符，并返回找到的字符或子字符串的索引值。

**真实例子:**

> 以一本书为例。这本书包含的页面包含单词。现在，如果用户想要找出他自己选择的一个单词的出现，那么读者的脑海中会出现这样的问题:要搜索的那个单词甚至存在于书中吗？如果存在，则在记住它最后出现的页面之前开始翻转页面，因为该单词可能会在他最后更新的页面之后重复，并且读完了这本书。
> 
> 这里，书中所有单词的集合称为“字符串”，要搜索的单词称为“单词”本身。这个词出现的确切位置被称为“索引”。

现在在 Java 中，已经有一个在字符串中定义的处理索引的内置方法，叫做 [indexOf()](https://www.geeksforgeeks.org/java-string-indexof/) 。它用于从给定字符串中找出特殊字符或子字符串本身的索引。通常，有两种可能，第一种是当字符串中有字符或子字符串时，它返回索引，如果没有，如果字符串中没有字符或子字符串，这个函数返回“-1”。-1 在 java 中是返回的，因为在 java 中，python 中不存在负索引的概念。

类似地**、**还有一个预定义的内置函数，定义为 [lastIndexOf()](https://www.geeksforgeeks.org/java-lang-string-lastindexof-method/) ，它指定字符串中字符或子字符串的最后一次出现。该方法从字符串的最后一个开始工作，并向后移动。现在，如果在 *lastIndexOf()* 方法的函数调用中指定了“ *fromIndex* ，则搜索字符或子字符串从“frontIndex”的前面开始，而不是字符串的最后一个。

*   **int lastIndexOf(int ch)** //返回字符串中字符出现的最后一个索引。

*   **int lastIndexOf(int ch，int fromIndex)** //返回从‘front Index’开始向后看的最后一个索引。

*   **int latindex of(String str)**//从字符串的最后一个返回名为“str”的子字符串的最后一个索引。

*   **int lastIndexOf(String str，int fromIndex)** //返回字符串中从 frontIndex 开始的子字符串的最后一次出现。

**内置功能所在的目录:**

```java
java.util.String.lastIndexOf()

```

**返回类型:**

*   正值:字符串中最后一个字符或子字符串匹配的值
*   ***-1*** 如果不匹配

**进场:**

*   创建一个名为的类。
*   用名称字符串声明一个变量，并用值“geeksforgeeks”初始化该变量
*   现在用名称词声明另一个变量 *ab* le，并用值初始化变量为“极客”。这个词是这个场景中的搜索词。
*   在用值初始化之后，现在我们可以使用 [lastIndexOf()](https://www.geeksforgeeks.org/java-lang-string-lastindexof-method/) 方法，并且应该传递字符串和单词作为参数。
*   完成上述步骤后，编译程序。
*   一旦程序被编译，你就会得到输出。

**示例 1:** 考虑到字符串中不存在字符或子字符串的位置，它将返回最后一个索引值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to  find the Last 
// Index of a particular word 
// in a string

// Importing Classes/Files
import java.util.*;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // String in which char or
        // substring to be searched
        String str = "geeksforgeeks";

        // Substring to be searched
        String word = "geeks";

        // Printing last index of char
        // or substring is found
        // Printing -1 is not found
        System.out.println(str.lastIndexOf(word));
    }
}
```

**Output**

```java
8
```

**示例 2:** 考虑到字符串中不存在字符或子字符串的位置，它将返回一个“-1”值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to  find the Last
// Index of a particular word 
// in a string

// Importing Classes/Files
import java.util.*;
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // String in which char or 
        // substring to be searched
        String str = "geeksforgeek";

        // Substring to be searched
        String word = "gfg";

        // Printing last index of char 
        // or substring is found
        // Printing -1 is not found
        System.out.println(str.lastIndexOf(word));
    }
}
```

**Output**

```java
-1
```