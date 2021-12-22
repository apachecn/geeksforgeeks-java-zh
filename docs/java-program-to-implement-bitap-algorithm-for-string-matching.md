# 实现字符串匹配 Bitap 算法的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-bitap-算法到字符串匹配/](https://www.geeksforgeeks.org/java-program-to-implement-bitap-algorithm-for-string-matching/)

**Bitap 算法**是一种近似字符串匹配算法。该算法告诉给定文本是否包含与给定模式“近似相等”的子串。这里近似相等表示如果子串和模式在给定的相互距离 k 内。该算法从预计算一组位掩码开始，该组位掩码包含模式每个元素的一个位。这将执行大多数快速的按位运算。

Bitap 算法也被称为**移位或、移位和**，或巴埃萨·耶茨·贡内特算法。

**示例:**

```
Input:
Text: geeksforgeeks
Pattern: geeks
Output:
Pattern found at index: 0

Input:
Text: Youareawesome
Pattern: Youareamazing
Output:
No Match.
```

**进场:**

*   以字符串形式输入文本模式。
*   我们将把这个字符串转换成一个简单的字符数组
*   如果长度为 0 或超过 63，我们返回“**不匹配”。**
*   现在，通过取补 0 的数组 R。
*   取一个补充 0 到 1 的数组“pattern_mask”
*   将模式作为“pattern_mask”的索引，然后通过使用 and 运算符，我们将它向左移动 I 倍，从而将它与 1L(长整数)的补码结果进行比较。
*   现在通过循环直到文本长度。
*   我们现在用 R 和图案蒙版对其进行**或**。
*   现在通过向左移动模式长度的 1L，结果是一个带 R 的**和**
*   如果它等于零，我们通过 I-len+1 打印它，否则返回-1
*   输出是模式匹配的文本索引。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to implement Bitap Algorithm.

import java.io.*;
import java.io.IOException;

public class GFG {
    public static void main(String[] args)
        throws IOException
    {

        System.out.println("Bitap Algorithm!");

        String text = "geeksforgeeks";

        String pattern = "geeks";

        // This is an object created of the class for
        // extension of functions.
        GFG g = new GFG();

        // Now here we go to findPattern functions , we two
        // arguments.
        g.findPattern(text, pattern);
    }

    public void findPattern(String t, String p)
    {

        // we convert the String text to Character Array for
        // easy indexing
        char[] text = t.toCharArray();

        // we convert the String pattern to Character Array
        // to access each letter in the String easily.
        char[] pattern = p.toCharArray();

        // Index shows the function bitap search if they are
        // equal at a particular index or not
        int index = bitap_search(text, pattern);

        // If the pattern is not equal to the text of the
        // string approximately Then we tend to return -1 If
        // index is -1 Then we print there is No match
        if (index == -1) {
            System.out.println("\nNo Match\n");
        }

        else {

            // Else if there is a match
            // Then we print the position of the index at
            // where the pattern and the text matches.
            System.out.println(
                "\nPattern found at index: \n" + index);
        }
    }

    private int bitap_search(char[] text, char[] pattern)
    {

        // Here the len variable is taken
        // This variable accepts the pattern length as its
        // value
        int len = pattern.length;

        // This is an array of pattern_mask of all
        // character values in it.

        long pattern_mask[]
            = new long[Character.MAX_VALUE + 1];

        // Here the variable of being long type is
        // complemented with 1;

        long R = ~1;

        // Now if the length of the pattern is 0
        // we would return -1
        if (len == 0) {
            return -1;
        }

        // Or if the length of the pattern exceeds the
        // length of the character array Then we would
        // declare that the pattern is too long. We would
        // return -1

        if (len > 63) {

            System.out.println("Pattern too long!");
            return -1;
        }

        // Now filling the values in the pattern mask
        // We would run th eloop until the max value of
        // character Initially all the values of Character
        // are put up inside the pattern mask array And
        // initially they are complemented with zero

        for (int i = 0; i <= Character.MAX_VALUE; ++i)

            pattern_mask[i] = ~0;

        // Now len being the variable of pattern length ,
        // the loop is set  till there Now the pattern being
        // the index of the pattern_mask 1L means the long
        // integer is shifted to left by i times The result
        // of that is now being complemented the result of
        // the baove is now being used as an and operator We
        // and the pattern_mask and the result of it

        for (int i = 0; i < len; ++i)
            pattern_mask[pattern[i]] &= ~(1L << i);

        // Now the loop is made to run until the text length
        // Now what we do this the R array is used
        // as an Or function with pattern_mask at index of
        // text of i

        for (int i = 0; i < text.length; ++i) {

            R |= pattern_mask];

            // Now  result of the r after the above
            // operation
            // we shift it to left side by 1 time

            R <<= 1;

            // If the 1L long integer if shifted left of the
            // len And the result is used to and the result
            // and R array
            // If that result is equal to 0
            // We return the index value
            // Index=i-len+1

            if ((R & (1L << len)) == 0)

                return i - len + 1;
        }

        // if the index is not matched
        // then we return it as -1
        // stating no match found.

        return -1;
    }
}
```

**Output**

```
Bitap Algorithm!

Pattern found at index: 
0
```