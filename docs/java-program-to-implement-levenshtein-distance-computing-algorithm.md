# 实现 Levenshtein 距离计算算法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序实现-levenshtein-距离计算-算法/](https://www.geeksforgeeks.org/java-program-to-implement-levenshtein-distance-computing-algorithm/)

**莱文斯坦距离**也称为**编辑距离**，是将一个字符串转换为另一个字符串所需的最小操作数。

通常，会执行三种类型的操作(一次一个) :

*   替换一个字符。
*   删除一个字符。
*   插入一个字符。

**示例:**

> 输入:str 1 = " glomax "，str 2 = " folmax "
> 
> 产出:3
> 
> 通过将“g”替换为“o”，删除第二个“o”，并在开头插入“f”，将 str1 转换为 str2。少于三次编辑是做不到的。
> 
> 输入:S1 =“GIKY”，S2 =“GEKEY”
> 
> 产出:2
> 
> s1 通过在“G”后面插入“E”并将“I”替换为“E”而转换为 s2。

**这个问题可以通过两种方式来完成:**

1.  使用递归。
2.  使用动态编程。

**方法 1:递归方法**

让我们举个例子来考虑一下

给定两个字符串 s1 =“星期日”和 s2 =“星期六”。我们想用最少的编辑把“星期天”转换成“星期六”。

*   将“I”和“j”视为使用 s1 和 s2 生成的子字符串的上限索引。
*   让我们选择 i = 2 和 j = 4，即前缀字符串分别是“su”和“satu”(假设字符串索引从 1 开始)。最右边的字符可以通过三种不同的方式对齐。
*   可能**情况 1** :将字符‘u’和‘u’对齐。它们是相等的，不需要编辑。我们仍然留下 i = 1 和 j = 3 的问题，所以我们应该继续寻找 Levenshtein 距离(i-1，j-1)。
*   可能**情况 2** (删除):对齐第一个字符串中的右边字符，不对齐第二个字符串中的任何字符。我们需要删除这里。我们还剩下 i = 1 和 j = 4 的问题，所以我们应该继续寻找 Levenshtein 距离(i-1，j)。
*   可能**情况 3** (插入):对齐第二个字符串的右边字符，不对齐第一个字符串的任何字符。我们需要在这里插入。我们仍然留下 i = 2 和 j = 3 的问题，所以我们应该继续寻找 Levenshtein 距离(I，j-1)。
*   我们假设要插入第一个字符串的字符与第二个字符串的右字符相同。
*   可能的**情况 4** (替换):从第一个字符串和第二个字符串中右对齐字符。我们需要一个替代品。我们还剩下 i = 1 和 j = 3 的问题，所以我们应该继续寻找 Levenshtein 距离(i-1，j-1)。
*   我们假设第一个字符串中被替换的字符与第二个字符串的右字符相同。
*   我们必须找到所有可能的三种情况中的最小值。

**递归实现:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of recursive Levenshtein distance
// calculation

import java.util.*;
class LevenshteinDistanceRecursive {

    static int compute_Levenshtein_distance(String str1,
                                            String str2)
    {
        // If str1 is empty, all
        // characters of str2 are
        // inserted into str1, which is
        // of the only possible method of
        // conversion with minimum
        // operations.

        if (str1.isEmpty())
        {
            return str2.length();
        }

        // If str2 is empty, all
        // characters of str1 are
        // removed, which is the
        // only possible
        // method of conversion with minimum
        // operations.

        if (str2.isEmpty()) 
        {
            return str1.length();
        }

        // calculate the number of distinct characters to be
        // replaced in str1
        // by recursively traversing each substring

        int replace = compute_Levenshtein_distance(
              str1.substring(1), str2.substring(1))
              + NumOfReplacement(str1.charAt(0),str2.charAt(0));

        // calculate the number of insertions in str1
        // recursively
        int insert = compute_Levenshtein_distance(
                         str1, str2.substring(1))+ 1;

        // calculate the number of deletions in str1
        // recursively
        int delete = compute_Levenshtein_distance(
                         str1.substring(1), str2)+ 1;

        // returns minimum of three operatoins

        return minm_edits(replace, insert, delete);
    }

    static int NumOfReplacement(char c1, char c2)
    {
        // check for distinct characters
        // in str1 and str2

        return c1 == c2 ? 0 : 1;
    }

    static int minm_edits(int... nums)
    {
        // receives the count of different
        // operations performed and returns the
        // minimum value among them.

        return Arrays.stream(nums).min().orElse(
            Integer.MAX_VALUE);
    }

    // Driver Code
    public static void main(String args[])
    {
        String s1 = "glomax";
        String s2 = "folmax";

        System.out.println(compute_Levenshtein_distance(s1, s2));
    }
}
```

**Output**

```
3
```

**时间复杂度:** O(3^n)因为在每一步，我们分支成三个递归调用。这里，n 是第一个字符串的长度。

**方法二:动态规划法**

如果我们画出上述解的递归树，我们可以看到相同的子问题被一次又一次地计算出来。我们知道，当子问题的解可以记忆而不是一次又一次地计算时，动态规划就出现了。

*   *记忆化*版本遵循自上而下的方法，因为我们首先将问题分解为子问题，然后计算并存储值。
*   我们也可以用自下而上的方法解决这个问题。以自下而上的方式，我们先解决子问题，然后再从中解决更大的子问题。

**动态编程实现(优化方法)**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of Levenshtein distance calculation
// Using Dynamic Programming (Optimised solution)

import java.util.*;
class LevenshteinDistanceDP {

    static int compute_Levenshtein_distanceDP(String str1,
                                              String str2)
    {

        // A 2-D matrix to store previously calculated
        // answers of subproblems in order
        // to obtain the final

        int[][] dp = new int[str1.length() + 1][str2.length() + 1];

        for (int i = 0; i <= str1.length(); i++) 
        {
            for (int j = 0; j <= str2.length(); j++) {

                // If str1 is empty, all characters of
                // str2 are inserted into str1, which is of
                // the only possible method of conversion
                // with minimum operations.
                if (i == 0) {
                    dp[i][j] = j;
                }

                // If str2 is empty, all characters of str1
                // are removed, which is the only possible
                //  method of conversion with minimum
                //  operations.
                else if (j == 0) {
                    dp[i][j] = i;
                }

                else {
                    // find the minimum among three
                    // operations below

                    dp[i][j] = minm_edits(dp[i - 1][j - 1]
                        + NumOfReplacement(str1.charAt(i - 1),str2.charAt(j - 1)), // replace
                        dp[i - 1][j] + 1, // delete
                        dp[i][j - 1] + 1); // insert
                }
            }
        }

        return dp[str1.length()][str2.length()];
    }

    // check for distinct characters
    // in str1 and str2

    static int NumOfReplacement(char c1, char c2)
    {
        return c1 == c2 ? 0 : 1;
    }

    // receives the count of different
    // operations performed and returns the
    // minimum value among them.

    static int minm_edits(int... nums)
    {

        return Arrays.stream(nums).min().orElse(
            Integer.MAX_VALUE);
    }

    // Driver Code
    public static void main(String args[])
    {

        String s1 = "glomax";
        String s2 = "folmax";

        System.out.println(compute_Levenshtein_distanceDP(s1, s2));
    }
}
```

**Output**

```
3
```

**时间复杂度:** O(m*n)，其中 m 为第一串的长度，n 为第二串的长度。

**辅助空间:** O(m*n)，因为上述实现中使用的矩阵有维度 **m*n** 。

**应用:**

*   拼写检查器。
*   语音识别。
*   基因分析。