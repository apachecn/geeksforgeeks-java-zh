# Java 字符串区域匹配()方法示例

> 原文:[https://www . geesforgeks . org/如何匹配 java 字符串中的区域/](https://www.geeksforgeeks.org/how-to-match-regions-in-strings-in-java/)

String 类的 **regionMatches()** 方法有两个变体，可以用来测试两个字符串区域是否匹配或相等。这种方法有两种变体，即一种是区分大小写的测试方法，另一种忽略区分大小写的方法。

**语法:**

**1。区分大小写的测试方法:**

```java
public boolean regionMatches(int toffset, String other, int ooffset, int len)
```

**2。它可以选择考虑或忽略案例方法:**

```java
public boolean regionMatches(boolean ignoreCase, int toffset, String other, int ooffset, int len)
```

**参数:**

*   **ignoreCase:** 如果为真，比较字符时忽略大小写。
*   **toffset:** 该字符串中子区域的起始偏移量。
*   **其他:**正在比较的字符串参数。
*   **ooffset:** 字符串参数中子区域的起始偏移量。
*   **len:** 要比较的字符数。

**返回值:**

将字符串对象的子字符串与参数 other 的子字符串进行比较。如果这些子字符串表示相同的字符序列，则结果为真，如果且仅当 ignoreCase 为真，则忽略大小写。要比较的字符串对象的子字符串从索引 toffset 开始，长度为 len。要比较的其他子串从索引 ooffset 开始，长度为 len。当且仅当下列至少一项为真时，结果为假

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to find if substrings
// or regions of two strings are equal

import java.io.*;

class CheckIfRegionsEqual {
    public static void main(String args[])
    {

        // create three string objects
        String str1
            = new String("Welcome to Geeksforgeeks.com");
        String str2 = new String("Geeksforgeeks");
        String str3 = new String("GEEKSFORGEEKS");

        // Comparing str1 and str2
        System.out.print(
            "Result of Comparing of String 1 and String 2: ");
        System.out.println(
            str1.regionMatches(11, str2, 0, 13));

        // Comparing str1 and str3
        System.out.print(
            "Result of Comparing of String 1 and String 3: ");
        System.out.println(
            str1.regionMatches(11, str3, 0, 13));

        // Comparing str2 and str3
        System.out.print(
            "Result of Comparing of String 2 and String 3: ");
        System.out.println(
            str2.regionMatches(0, str3, 0, 13));
    }
}
```

**Output**

```java
Result of Comparing of String 1 and String 2: true
Result of Comparing of String 1 and String 3: false
Result of Comparing of String 2 and String 3: false
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to find if substrings
// or regions of two strings are equal

import java.io.*;

class CheckIfRegionsEqual {
    public static void main(String args[])
    {

        // create three string objects
        String str1 = new String("Abhishek Rout");
        String str2 = new String("abhishek");
        String str3 = new String("ABHISHEK");

        // Comparing str1 and str2 substrings
        System.out.print(
            "Result of comparing String 1 and String 2 : ");
        System.out.println(
            str1.regionMatches(true, 0, str2, 0, 8));

        // Comparing str1 and str3 substrings
        System.out.print(
            "Result of comparing String 1 and String 3 : ");
        System.out.println(
            str1.regionMatches(false, 0, str3, 0, 8));

        // Comparing str2 and str3 substrings
        System.out.print(
            "Result of comparing String 2 and String 3 : ");
        System.out.println(
            str2.regionMatches(true, 0, str3, 0, 8));
    }
}
```

**Output**

```java
Result of comparing String 1 and String 2 : true
Result of comparing String 1 and String 3 : false
Result of comparing String 2 and String 3 : true
```

**注意:**如果其中至少一个为真，则该方法返回假，

*   toffset 为负。
*   ooffset 为负。
*   toffset+len 大于此 String 对象的长度。
*   ooffset+len 大于另一个参数的长度。
*   ignoreCase 为 false，且有一些小于 len 的非负整数 *k* ，这样:

```java
 this.charAt(toffset+k) != other.charAt(ooffset+k)
```

*   ignoreCase 为真，有一些非负整数 *k* 小于 len，这样:

```java
 Character.toLowerCase(Character.toUpperCase(this.charAt(toffset+k))) != 
     Character.toLowerCase(Character.toUpperCase(other.charAt(ooffset+k)))
```