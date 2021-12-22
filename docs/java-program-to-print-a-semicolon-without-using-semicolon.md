# 不使用分号打印分号的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-打印-不使用分号的分号/](https://www.geeksforgeeks.org/java-program-to-print-a-semicolon-without-using-semicolon/)

给定的任务是打印一个'**；**【不用】**；**'代码中的任何地方。人们能想到的解决这个有趣问题的最简单的方法是在程序中使用 ASCII 值。但由于 Java 不支持宏，不像 C/C++，因此要剔除“**；”**在代码中的每一行的末尾都是使用，if-语句或 while 循环在条件语句中用 [**printf** (String，Object)方法的 **PrintStream**](https://www.geeksforgeeks.org/printstream-printfstring-object-method-in-java-with-examples/) 。这里的主要逻辑是 **printf()** 返回 [PrintStream](https://www.geeksforgeeks.org/java-io-printstream-class-java-set-1/) 对象，该对象不是空的，因此将其与空值(Java 中的文字)进行比较，我们将获得所需的输出。

**方法 1:使用 if 语句**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print ; without using ;
// using if statement

class PrintSemicolonExample {
    public static void main(String[] args)
    {
        // The ASCII value for semicolon is 59
        if (System.out.printf("%C", 59) == null) {
        }
    }
}
```

**Output**

```java
;

```

**方法二:边循环边使用**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print ; without using ;
// using while loop

class PrintSemicolonExample {
    public static void main(String[] args)
    {
        while ((System.out.printf("%C", 59) == null)) {
        }
    }
}
```

**Output**

```java
;

```