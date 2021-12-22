# 计算字符串位数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序对计数-字符串位数/](https://www.geeksforgeeks.org/java-program-to-count-number-of-digits-in-a-string/)

[字符串](https://www.geeksforgeeks.org/string-class-in-java/)是一个字符序列。在 java 中，String 的对象是不可变的。不可变意味着一旦对象被创建，它的内容就不能改变。要找到字符串中的总位数，需要在字符串中完成遍历。

**示例:**

```
Input : string = "GeeksforGeeks password is : 1234"
Output: Total number of Digits = 4

Input : string = "G e e k s f o r G e e k 1234"
Output: Total number of Digits = 4
```

**进场:**

1.  创建一个整数变量并用 0 初始化它。
2.  开始字符串遍历。
3.  如果当前索引处字符的 ASCII 码大于或等于 48，小于或等于 57，则递增变量。
4.  遍历结束后，打印变量。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Count Number of Digits in a String
public class GFG {

    public static void main(String[] args)
    {
        String str = "GeeksforGeeks password is : 1234";
        int digits = 0;
        for (int i = 0; i < str.length(); i++) {
            if (str.charAt(i) >= 48 && str.charAt(i) <= 57)
                digits++;
        }
        System.out.println("Total number of Digits = "
                           + digits);
    }
}
```

**Output**

```
Total number of Digits = 4
```

**时间复杂度:** O(N)，其中 N 为字符串的长度。