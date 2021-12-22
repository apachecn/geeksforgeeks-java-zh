# Java 程序添加两个二进制字符串

> 原文:[https://www . geesforgeks . org/Java-程序添加二进制字符串/](https://www.geeksforgeeks.org/java-program-to-add-two-binary-strings/)

当两个二进制字符串相加时，返回的总和也是一个二进制字符串。

**示例:**

```java
Input :  x = "10", y = "01"
Output: "11"

Input :  x = "110", y = "011"
Output: "1001"
Explanation:
  110 
+ 011
=1001
```

这里，我们需要从右侧开始相加，当返回的总和大于 1 时，存储下一个数字的进位。

*为了得到上述题目的清晰概念，我们来看一个程序。*

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// java program to add two binary strings

public class gfg {

    // Function to add two binary strings
    static String add_Binary(String x, String y)
    {

        // Initializing result
        String res = "";

        // Initializing digit sum
        int d = 0;

        // Traversing both the strings starting
        // from the last characters
        int k = x.length() - 1, l = y.length() - 1;
        while (k >= 0 || l >= 0 || d == 1) {

            // Computing the sum of last
            // digits and the carry
            d += ((k >= 0) ? x.charAt(k) - '0' : 0);
            d += ((l >= 0) ? y.charAt(l) - '0' : 0);

            // When the current digit's sum is either
            // 1 or 3 then add 1 to the result
            res = (char)(d % 2 + '0') + res;

            // Computing carry
            d /= 2;

            // Moving to the next digits
            k--;
            l--;
        }

        return res;
    }

    // The Driver code
    public static void main(String args[])
    {
        String x = "011011", y = "1010111";

        System.out.print(add_Binary(x, y));
    }
}
```

**Output**

```java
1110010
```