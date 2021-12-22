# 实现短文本大小字符串搜索算法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-实现短文本大小的字符串搜索算法的程序/](https://www.geeksforgeeks.org/java-program-to-implement-the-string-search-algorithm-for-short-text-sizes/)

**模式搜索是计算机科学中一个至关重要的问题。当我们在记事本/word 文件或浏览器或数据库中搜索字符串时，会使用模式搜索算法来显示搜索结果。**

**一个典型的问题陈述是-
给定一个文本 txt[0..n-1]和模式 pat[0..m-1]，编写一个函数搜索(char pat[]，char txt[])，打印出所有出现在 txt[]中的 pat[]。**

****示例:****

```java
Input:  txt[] = "THIS IS A TEST TEXT"
        pat[] = "TExT"
Output: Pattern found at index 15

Input:  txt[] =  "AABAACAADAABAABA"
        pat[] =  "AABA"
Output: Pattern found at index 0
        Pattern found at index 9
        Pattern found at index 12
```

**在这个程序中，给定一个文本和一个模式作为输入，在文本中搜索一个模式，我们得到模式的所有实例作为输出。**

****算法:****

*   **以文字和图案为输入。**
*   **运行一个从 0 到模式文本长度的外部 for 循环。**
*   **运行从 0 到模式长度的内部循环。**
*   **通过这种方式，对于文本中从索引开始直到索引+模式长度的每个索引处的每个字符，在文本中搜索模式。**
*   **如果找到模式，打印在文本中找到该模式的外循环索引。**
*   **否则如果找不到图案，就打印出来。**

**下面是上述方法的实现:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to Implement the String Search
// Algorithm for Short Text Sizes

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        String text = "geeksforgeeks is a coding website for geeks";
        String pattern = "geeks";

        // calling the method that is designed for
        // printing the instances of pattern
        // found in the text string
        stringMatch(text, pattern);
    }
    public static void stringMatch(String text, String pattern)
    {

        int len_t = text.length();
        int len_p = pattern.length();

        int k = 0, i = 0, j = 0;

        // loop to find out the position Of searched pattern
        for (i = 0; i <= (len_t - len_p); i++) {

            for (j = 0; j < len_p; j++)
            {
                if (text.charAt(i + j) != pattern.charAt(j))
                    break;
            }

            if (j == len_p)
            {
                k++;
                System.out.println("Pattern Found at Position: " + i);
            }
        }

        if (k == 0)
            System.out.println("No Match Found!");
        else
            System.out.println("Total Instances Found = " + k);
    }
}
```

****Output**

```java
Pattern Found at Position: 0
Pattern Found at Position: 8
Pattern Found at Position: 38
Total Instances Found = 3

```** 

****最坏情况时间复杂度:** O(m(n-m+1))**

**[**有效进场:**](https://www.geeksforgeeks.org/kmp-algorithm-for-pattern-searching/)**

**KMP 算法是搜索文本内部模式的有效方法。当检测到不匹配时遍历，下一个窗口的文本中的一些字符是已知的。利用这一优势，时间复杂度降低到 0(n)。**

**以下是有效方法的实施:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to Implement the String Search
// Algorithm for Short Text Sizes

class KMP_String_Matching {
    void KMPSearch(String pat, String txt)
    {
        int M = pat.length();
        int N = txt.length();

        // create lps[] that will hold the longest
        // prefix suffix values for pattern
        int lps[] = new int[M];
        int j = 0; // index for pat[]

        // Preprocess the pattern (calculate lps[]
        // array)
        computeLPSArray(pat, M, lps);

        int i = 0; // index for txt[]
        while (i < N) {
            if (pat.charAt(j) == txt.charAt(i)) {
                j++;
                i++;
            }
            if (j == M) {
                System.out.println("Found pattern "
                                   + "at index " + (i - j));
                j = lps[j - 1];
            }

            // mismatch after j matches
            else if (i < N
                     && pat.charAt(j) != txt.charAt(i)) {
                // Do not match lps[0..lps[j-1]] characters,
                // they will match anyway
                if (j != 0)
                    j = lps[j - 1];
                else
                    i = i + 1;
            }
        }
    }

    void computeLPSArray(String pat, int M, int lps[])
    {
        // length of the previous longest prefix suffix
        int len = 0;
        int i = 1;
        lps[0] = 0; // lps[0] is always 0

        // the loop calculates lps[i] for i = 1 to M-1
        while (i < M) {
            if (pat.charAt(i) == pat.charAt(len)) {
                len++;
                lps[i] = len;
                i++;
            }
            else // (pat[i] != pat[len])
            {
                // This is tricky. Consider the example.
                // AAACAAAA and i = 7\. The idea is similar
                // to search step.
                if (len != 0) {
                    len = lps[len - 1];

                    // Also, note that we do not increment
                    // i here
                }
                else // if (len == 0)
                {
                    lps[i] = len;
                    i++;
                }
            }
        }
    }

    // Driver program to test above function
    public static void main(String args[])
    {
        String text
            = "geeksforgeeks is a coding website for geeks";
        String pattern = "geeks";

        KMP_String_Matching effective
            = new KMP_String_Matching();
        effective.KMPSearch(pattern, text);
    }
}
```

****Output**

```java
Found pattern at index 0
Found pattern at index 8
Found pattern at index 38

```** 

****时间复杂度:** O(n)**