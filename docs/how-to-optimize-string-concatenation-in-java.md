# 如何在 Java 中优化字符串拼接？

> 原文:[https://www . geesforgeks . org/如何在 java 中优化字符串串联/](https://www.geeksforgeeks.org/how-to-optimize-string-concatenation-in-java/)

[**字符串**](https://www.geeksforgeeks.org/string-data-structure/) 被定义为一个字符数组。字符数组和字符串的区别在于字符串以特殊字符“\0”结尾。因为数组是不可变的(不能增长)，所以字符串也是不可变的。每当对字符串进行更改时，就会创建一个全新的字符串。

**拼接**是端到端连接的过程。让我们举个例子来理解串联在英语中的意思。

```java
Person 1 speaking to Person 2 - ItsCodingEra
Person 2 speaking to Person 1 - 2020India

Now, let us carry a process whose output is as follows- ItsCodingEra2020India

This process is called concatenation.
```

**示例:**

```java
Input String = "Geeks" + "for" + "Geeks";
OutputString = "GeeksforGeeks" ;
```

我们有许多方法可以告诉计算机这样做，这些方法被称为方法。让我们描述计算机如何通过我们的方法以不同的方式执行一个动作。

**该动作可通过 4 种方法发生**:

*   使用**“+”运算符**
*   使用**串联(I)**内置方法
*   使用**字符串生成器**
*   使用 **StringBuffer**

让我们逐一描述和实现它们。

**方法 1:使用“+”运算符的字符串连接**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to concatenate string
import java.lang.*;

class GFG {

    public static void main(String[] args)
    {
        String str = "";

        // timer-start time
        long startTime = System.currentTimeMillis();

        for (int i = 0; i < 100000; i++) {
            // string concatenation
            str += Integer.toString(0);
        }

        // timer-end time
        long endTime = System.currentTimeMillis();

        // display the result
        System.out.println(
            "Time taken to concatenate 100000 Strings using '+' operator : "
            + (endTime - startTime) + " ms");
    }
}
```

**Output**

```java
Time taken to concatenate 100000 Strings using '+' operator : 2126 ms
```

**方法二:使用 concat()内置函数**

**Concat(String str)方法**将指定的字符串连接到该字符串的末尾。此方法在给定字符串的末尾追加指定的字符串，并返回组合字符串。

**示例:**

```java
String str="GeeksforGeeks";
s1 = s1.concat(".").concat("com");
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to concatenate string
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {
        String str = "";
        long startTime = System.currentTimeMillis();

        for (int i = 0; i < 100000; i++) {
            str.concat(Integer.toString(0));
        }

        long endTime = System.currentTimeMillis();
        System.out.println(
            "Time taken to concatenate 100000 Strings using concat() method : "
            + (endTime - startTime) + " ms");
    }
}
```

**Output**

```java
Time taken to concatenate 100000 Strings using concat() method : 46 ms
```

**方法 3:使用 StringBuilder(最佳方式)**

**StringBuilder** 代表一个可变的字符序列。因为 Java 中的字符串类创建了一个不可变的字符序列，所以 StringBuilder 类提供了一个字符串类的替代，因为它创建了一个可变的字符序列。

**示例:**

```java
StringBuilder str  = new StringBuilder();  
str.append("GFG");
```

**使用 StringBuilder 方法进行拼接的时间复杂度:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to concatenate string
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {
        StringBuilder str = new StringBuilder();
        long startTime = System.currentTimeMillis();

        for (int i = 0; i < 100000; i++) {
            str.append(0);
        }
        long endTime = System.currentTimeMillis();
        System.out.println(
            "Time taken to concatenate 100000 Strings using StringBuilder append : "
            + (endTime - startTime) + " ms");
    }
}
```

**Output**

```java
Time taken to concatenate 100000 Strings using StringBuilder append : 34 ms
```

**方法 4:使用 StringBuffer**

**StringBuffer** 是 String 的对等类，提供了字符串的大部分功能。该字符串表示固定长度、不可变的字符序列，而 StringBuffer 表示可增长和可写的字符序列。

**示例:**

```java
StringBuffer s = new StringBuffer("GeeksforGeeks");
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to concatenate string
import java.lang.*;

class GFG {
    public static void main(String[] args)
    {
        StringBuffer str = new StringBuffer();
        long startTime = System.currentTimeMillis();

        for (int i = 0; i < 100000; i++) {
            str.append(0);
        }

        long endTime = System.currentTimeMillis();

        System.out.println(
            "Time taken to concatenate 100000 Strings using StringBuffer append : "
            + (endTime - startTime) + " ms");
    }
}
```

**Output**

```java
Time taken to concatenate 100000 Strings using StringBuffer append : 41 ms
```