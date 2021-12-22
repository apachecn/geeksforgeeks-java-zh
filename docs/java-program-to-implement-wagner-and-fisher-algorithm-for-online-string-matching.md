# 实现在线字符串匹配瓦格纳和费希尔算法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-implement-Wagner-and-fisher-algorithm-for-online-string-matching/](https://www.geeksforgeeks.org/java-program-to-implement-wagner-and-fisher-algorithm-for-online-string-matching/)

瓦格纳-菲舍尔算法是一种**动态编程算法**，用于测量两个字符串之间的列文斯坦距离或编辑距离。Levenshtein Distance(LD)计算这两个字符串的相似程度。通过三个参数计算距离，将 string1 转换为 string2。

参数为:

*   Number of deletions

**例如**

```
 Input:  str1="cat"  str2="cat"
 Output: 0

 The levenshtein distance i.e. LD(str1,str2)=0, because both the strings 
 are equal and no changes are needed.

 Input:  str1="bat"   str2="cat"
 Output: 1

 The levenshtein distance i.e. LD(str1,str2)=1, because we need to 
 substitute 'b' with 'c' to transform the string1 to string2.

 Input:  str1="bat"   str2="ball"
 Output: 2

 The levenshtein distance i.e. LD(str1,str2)=2, because there is 
 one substitution of 't' to 'l' and one insertion of 'l' needed to
 transform "bat" to "ball".
```

**算法:**

*   将字符串 str1 和 str2 的长度分别存储在一些变量中，比如 n 和 m。
*   如果 n==0，返回 m
*   如果 m==0，返回 n
*   构造 m 行 n 列的矩阵，将第一行初始化为 0 到 n，第一列初始化为 0 到 m。
*   检查 str1 的每个字符和 str2 的每个字符。
*   如果 str1[i]处的字符等于 str2[j]处的字符，则 m 为 0，如果两者不相等，则 m 为 1。
*   将矩阵的 arr[i][j]处的元素设置为以下的最小值:(arr[i-1][j]+1，arr[i][j-1]+1，arr[i-1][j-1]+m)
*   在重复步骤 5、6、7 之后，距离在 arr[n][m]处找到。

**代码:**

## Java

```
// Java Program to Implement Wagner and Fisher
// Algorithm for online String Matching

import java.util.*;

class GFG {
    public static int getDistance(String str1, String str2)
    {

        int l1 = str1.length();
        int l2 = str2.length();

        if (l1 == 0)
            return l2;

        if (l2 == 0)
            return l1;

        int arr[][] = new int[l1 + 1][l2 + 1];

        for (int i = 0; i <= l1; i++)
            arr[i][0] = i;

        for (int j = 0; j <= l2; j++)
            arr[0][j] = j;

        for (int i = 1; i <= l1; i++) {
            char ch1 = str1.charAt(i - 1);

            for (int j = 1; j <= l2; j++) {
                char ch2 = str2.charAt(j - 1);

                int m = ch1 == ch2 ? 0 : 1;

                arr[i][j] = Math.min(
                    Math.min((arr[i - 1][j] + 1),
                             (arr[i][j - 1] + 1)),
                    arr[i - 1][j - 1] + m);
            }
        }

        return arr[l1][l2];
    }

    public static void main(String[] args)
    {

        String str1, str2;

        str1 = "bat";
        str2 = "ball";

        System.out.println(getDistance(str1, str2));
    }
}
```

**输出**

```
2
```

**时间复杂度:** O(m*n)。