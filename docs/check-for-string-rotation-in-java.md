# 检查 Java 中的字符串旋转

> 原文:[https://www . geesforgeks . org/check-for-string-rotation-in-Java/](https://www.geeksforgeeks.org/check-for-string-rotation-in-java/)

给定两个字符串 s1 和 s2，写一个片段来检查 s2 是否是 s1 的旋转。字符串可能包含重复项。

示例:

```
Input :  s1 = "ABCD", s2 = "CDAB"
Output : True
String s1 is rotation of s2.

Input :  s1 = "ABAD", s2 = "ADAB"
Output : True

Input : s1 = ABCD, and s2 = ACBD 
Output : False

```

一个**简单的解决方法**是在 s2 中搜索 s1 的第一个出现。对于每个匹配，检查剩余字符串是否循环匹配。

一个**有效的解决方案**是把 s1 和它自己连接起来。当且仅当 s2 是旋转字符串的子串时，S2 是 s1 的旋转。在 java 中，我们可以使用包含的[字符串或者](https://www.geeksforgeeks.org/java-string-contains-method-example/)的[索引来检查子字符串。](https://www.geeksforgeeks.org/javascript-array-indexof/)

```
// Java program to check if two given strings are
//  rotations of each other

class StringRotation {

    /* Function checks if passed strings (str1 and str2)
       are rotations of each other */
    static boolean areRotations(String str1, String str2)
    {
        // There lengths must be same and str2 must be
        // a substring of str1 concatenated with str1.
        return (str1.length() == str2.length()) && 
               ((str1 + str1).contains(str2));
    }

    // Driver method
    public static void main(String[] args)
    {
        String str1 = "AACD";
        String str2 = "ACDA";

        if (areRotations(str1, str2))
            System.out.println("Yes");
        else
            System.out.printf("No");
    }
}
```

[**输出:**

```
Yes

```](https://www.geeksforgeeks.org/javascript-array-indexof/)