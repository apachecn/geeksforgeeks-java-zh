# 用 Java 打印字符串前 K 个字符的不同方法

> 原文:[https://www . geesforgeks . org/不同的打印方式-java 字符串中的第一个 k 字符/](https://www.geeksforgeeks.org/different-ways-to-print-first-k-characters-of-the-string-in-java/)

给定一个字符串 **str** 和一个正整数 **k** ，任务是编写一个 [Java](https://www.geeksforgeeks.org/java/) 程序来打印字符串的前 k 个字符。如果字符串长度小于 k，则按原样打印字符串。

**示例:**

> **输入:** str = "GeeksForGeeks "，k = 5
> 
> **输出:**极客
> 
> **说明:**给定字符串的前 k 个字符为‘Geeks’。
> 
> **输入:** str = "Geeks "，k = 6
> 
> **输出:**极客
> 
> **说明:**给定字符串的长度小于 k，因此我们按原样打印字符串。

### 方法 1:使用字符串长度

1.  获取字符串和正整数 k，打印字符串的前 k 个字符。
2.  检查字符串是否为空，然后返回 null。
3.  检查字符串长度是否大于 *k* ，然后使用 [str.substring(0，k)](https://www.geeksforgeeks.org/substring-in-java/) 获取字符串的前 k 个字符。
4.  如果字符串长度小于 k，则按原样返回字符串。
5.  现在，打印字符串的前 k 个字符。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print first k
// characters of the string

class GFG {

    // Function to print first k
    // characters of the string
    public static String 
      firstKCharacters(String str, int k)
    {

        // Check if the string is empty
        // or null then return null
        if (str == null || str.isEmpty())
            return null;

        // Check if the string length
        // is greater than k, then
        // get the first k characters 
        // of the string, otherwise
        // return the string as it is
        if (str.length() > k)
            return str.substring(0, k);

        else
            return str;
    }

    // Driver Code
    public static void main(String args[])
    {
        // Given String str
        String str = "GeeksForGeeks";

        // Given a positive integer k
        int k = 5;

        // Print the first k characters
        // of the string
        System.out.println(
          firstKCharacters(str, k));
    }
}
```

**Output**

```java
Geeks

```

### 方法 2:不检查大小

1.  想法是使用 [Math.min()](https://www.geeksforgeeks.org/java-math-min-method-examples/) 函数作为子串方法的结束索引。
2.  找出字符串长度和正整数 k 之间的最小值。
3.  获取从零到字符串长度和 k 的最小值的子字符串。
4.  现在，打印字符串的前 k 个字符。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print first k
// characters of the string

class GFG {

    // Function to print first k
    // characters of the string
    public static String firstKCharacters(String str, int k)
    {
        // Check if the string is
        // null or empty then
        // return null
        if (str == null || str.isEmpty())
            return null;

        // Return the first k characters
        // of the string if the string
        // length is less than k, otherwise
        // return the string as it is
        return str.substring(0, Math.min(str.length(), k));
    }

    // Driver Code
    public static void main(String args[])
    {
        // Given String str
        String str = "GeeksForGeeks";

        // Given a positive integer k
        int k = 5;

        // Print the first k characters
        // of the string
        System.out.println(firstKCharacters(str, k));
    }
}
```

**Output**

```java
Geeks

```