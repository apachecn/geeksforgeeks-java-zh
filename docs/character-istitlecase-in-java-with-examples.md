# Java 中的 Character.isTitleCase()带示例

> 原文:[https://www . geesforgeks . org/character-istitlecase-in-Java-with-examples/](https://www.geeksforgeeks.org/character-istitlecase-in-java-with-examples/)

java 内置方法中的**Java . lang . character . istitlecase()**，用于确定指定的字符是否为标题字符。如果由 **getType(代码点)**提供的通用类别类型是 **TITLECASE_LETTER** ，则字符是一个 titlecase 字符。
有些字符看起来像一对对拉丁字母。例如，有一个看起来像“lj”的大写字母和一个看起来像“LJ”的相应小写字母。第三种形式，看起来像“Lj”，是以小写字母和大写字母呈现单词时使用的合适形式，就像书的标题一样。

下面给出了该方法返回 true 的一些 Unicode 字符:

1.  带小写字母 Z 的拉丁文大写字母 D 随卡隆
2.  带小写字母 J 的拉丁文大写字母 L
3.  带小写字母 J 的拉丁文大写字母 N
4.  带小写字母 Z 的拉丁文大写字母 D

**语法:**

```java
public static boolean isTitleCase(char ch)

```

**参数:**该函数只接受一个强制参数 **ch** ，表示要测试的字符。

**返回值:**如果字符是 titlecase，这个方法返回 true，否则返回 false。

下面的程序说明了 isTitleCase()方法:

```java
// Java program to demonstrate
// Character.isTitleCase() method
import java.lang.*;
public class gfg {

    public static void main(String[] args)
    {

        // Assign values to ch1, ch2
        char ch1 = 'Z';
        char ch2 = '\u01f2';

        // Function to check if the
        // character is a title case or not
        boolean b1 = Character.isTitleCase(ch1);
        boolean b2 = Character.isTitleCase(ch2);

        System.out.println(ch1 + " is a titlecase character is " + b1);
        System.out.println("unicode \u01f2 is a titlecase character is " + b2);
    }
}
```

**Output:**

```java
Z is a titlecase character is false
unicode ? is a titlecase character is true

```