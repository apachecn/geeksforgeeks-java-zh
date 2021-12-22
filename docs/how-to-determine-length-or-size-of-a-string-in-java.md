# 如何在 Java 中确定字符串的长度或大小？

> 原文:[https://www . geesforgeks . org/如何确定 java 中字符串的长度或大小/](https://www.geeksforgeeks.org/how-to-determine-length-or-size-of-a-string-in-java/)

Java 中的字符串是由字符数组内部支持的对象。由于数组是不可变的，而字符串也是一种保存字符的特殊数组，因此字符串也是不可变的。

Java 的[字符串类包含很多对字符串执行各种操作的方法，如 compare()、concat()、equals()、split()、length()、replace()、compareTo()、substring()等。在这些方法中，我们将重点讨论**长度()**方法。](https://www.geeksforgeeks.org/strings-in-java/)

### 你所说的字符串的长度或大小是什么意思？

字符串的长度或大小是指其中存在的字符总数。

**例如–**字符串“极客为极客”有 15 个字符(也包括空格)。

### **String.length()** 方法

length()方法是一种适用于字符串对象的方法。length()方法返回字符串中存在的字符数。length()方法适用于字符串对象，但不适用于数组。

length()方法也可以用于 StringBuilder 和 StringBuffer 类。length()方法是一个公共成员方法。String 类、StringBuilder 类和 StringBuffer 类的任何对象都可以使用**访问 length()方法。**(点)运算符。

**方法签名–**length()方法的方法签名如下–

```java
public int length()  
```

**返回类型–**length()方法的返回类型是 **int。**

下面是如何使用 length()方法获得 Java 中字符串长度的例子–

**示例 1:** Java 程序演示如何用 length()方法获取 Java 中 String 的长度

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// how to get the length of String
// in Java using length() method

public class Test {
    public static void main(String[] args)
    {
        // Here str is a string object
        String str = "GeeksforGeeks";

        System.out.println(
            "The size of "
            + "the String is "
            + str.length());
    }
}
```

**Output**

```java
The size of the String is 13
```

**例 2:** Java 程序说明如何使用 length()方法检查两个字符串的长度是否相等。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate how to check
// whether the length of two strings is
// equal or not using the length() method.

import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        String s1 = "abc";
        String s2 = "xyz";

          // storing the length of both the
          // strings in int variables
        int len1 = s1.length();
        int len2 = s2.length();

          // checking whether the length of
          // the strings is equal or not
        if (len1 == len2) {
            System.out.println(
                "The length of both the strings are equal and is " + len1);
        }
        else {
            System.out.println(
                "The length of both the strings are not equal");
        }
    }
}
```

**Output**

```java
The length of both the strings are equal and is 3
```