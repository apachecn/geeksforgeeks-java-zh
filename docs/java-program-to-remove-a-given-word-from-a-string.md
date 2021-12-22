# 从字符串中删除给定单词的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-remove-从字符串中给定单词/](https://www.geeksforgeeks.org/java-program-to-remove-a-given-word-from-a-string/)

给定一个字符串和一个单词，任务是从字符串中删除该单词，否则返回-1 作为输出。为了更清楚，请查看下面给出的图示。

插图:

```java
Input    : This is the Geeks For Geeks
           word="the"
Output   : This is Geeks For Geeks

Input    :  Hello world Hello"  
           word = Hello
Output   : world
Explanation: The given string contains the word two times

Input    : Hello world  
           word = GFG
Output   : Hello world
Explanation: word doesn't exists in the string
```

现在为了达到目标，我们将讨论两种方法，即:

1.  使用搜索技术的简单方法
2.  使用[字符串替换()方法](https://www.geeksforgeeks.org/java-lang-string-replace-method-java/#:~:text=String%20replace()%20%3A%20This%20method,newch%20%3A%20the%20new%20character.)的最佳方法

**方法 1:** 使用搜索技术

*   将字符串转换为字符串数组。
*   迭代数组并检查与给定单词不相等的单词。
*   将单词连接成新的字符串数组名称作为新字符串。
*   打印新字符串。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Remove a Given Word From a String
// using searching techniques

// Importing input output classes
import java.io.*;

// main class
class GFG {

    // Method 1
    // To remove the word
    static void remove(String str, String word)
    {
        // Split the string using split() method
        String msg[] = str.split(" ");
        String new_str = "";

        // Iterating the string using for each loop
        for (String words : msg) {

            // If desired word is found
            if (!words.equals(word)) {

                // Concate the word not equal to the given
                // word
                new_str += words + " ";
            }
        }

        // Print the new String
        System.out.print(new_str);
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // Custom string as input
        String str = "This is the Geeks For Geeks";

        // Word to be removed from above string
        String word = "the";

        // Calling the method 1 by passing both strings to
        // it
        remove(str, word);
    }
}
```

**Output**

```java
This is Geeks For Geeks 
```

**方法二:**使用[弦.替换()方法](https://www.geeksforgeeks.org/java-lang-string-replace-method-java/#:~:text=String%20replace()%20%3A%20This%20method,newch%20%3A%20the%20new%20character.)

1.  这个方法接受两个输入的旧单词和 regex 格式的新单词。
2.  用新词替换所有旧词。
3.  返回结果字符串。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Remove a Given Word From a String

// Importing input output classes
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Given String as input from which
        // word has to be removed
        String str = "This is the Geeks For Geeks";

        // Desired word to be removed
        String word = "the";

        // Replace all words by "" string
        // using replaceAll() method
        str = str.replaceAll("the", "");

        // Trim the string using trim() method
        str = str.trim();

        // Printing the final string
        System.out.print(str);
    }
}
```

**Output**

```java
This is  Geeks For Geeks
```