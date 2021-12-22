# Java 中的 Java.lang.String.copyValueOf()

> 原文:[https://www . geesforgeks . org/Java-lang-string-copy value of-Java/](https://www.geeksforgeeks.org/java-lang-string-copyvalueof-java/)

copyValueOf()主要是将字符数组的内容复制到字符串中。这个函数有两种变体，本文将讨论这两种变体。
**实施 1 :**

```java
Syntax:
public static String copyValueOf(char[] ch)
Parameters:
ch : The character array.
Return Value : 
This function returns the string with the contents of character array copied 

```

```java
// Java code to demonstrate the working of 
// copyValueOf implementation 1 
public class Copy1 {
  public static void main(String args[]) {

    // Initialising Character array
     char[] ch = {'A', 's', 't', 'h', 'a', ' ', 'T', 'y', 'a', 'g', 'i'};

     // Initialising String
     String ch2 = "";

     // Copying value in ch2
     // now ch2 is equal to "Astha Tyagi"
     ch2 = ch2.copyValueOf( ch );

     // Printing String
     System.out.println("The new copied string is : " + ch2);
  }
}
```

输出:

```java
The new copied string is : Astha Tyagi

```

在第二种实现中，也可以提取子阵列而不是整个阵列。
**实施 2 :**

```java
Syntax:
public static String copyValueOf(char[] ch, int index, int num)
Parameters:
ch : The character array.
index :  The starting position of array from which copy is to start.
num :  Number of elements that has to be copied. 
Return Value : 
This function returns the string with the contents of character array copied

```

```java
// Java code to demonstrate the working of 
// copyValueOf implementation 2
public class Copy2 {
  public static void main(String args[]) {

    // Initialising Character array
     char[] ch = {'A', 's', 't', 'h', 'a', ' ', 'T', 'y', 'a', 'g', 'i'};

     // Initialising String
     String ch2 = "";

     // Copying value in ch2
     // only first 5 are extracted
     // now ch2 is equal to "Astha"
     ch2 = ch2.copyValueOf( ch , 0, 5 );

     // Printing String
     System.out.println("The new copied string is : " + ch2);
  }
}
```

输出:

```java
The new copied string is : Astha

```

**可能的应用:**该函数可用于使用实现 2 从字符串中常规复制或仅提取前缀或后缀。一个可能的例子是从处理面额的给定“1000 卢比”类型的字符串中仅提取金额。

```java
// Java code to demonstrate the application of 
// copyValueOf 
public class Appli2 {
  public static void main(String args[]) {

    // Initialising Character array
     char[] ch = {'R', 's', ' ', '1', '0', '2', '4' };

     // Original array
     System.out.print("The original array is : ");
     for (int i=0; i< ch.length ; i++) 
     System.out.print(ch[i]);

      System.out.print("\n");

     // Initialising String
     String ch2 = "";

     // Copying value in ch2
     // Rs is not included
     // now ch2 is equal to "1024"
     ch2 = ch2.copyValueOf( ch , 3, 4 );

     // Printing String
     System.out.println("The new string is : " + ch2);
  }
}
```

输出:

```java
The original array is : Rs 1024
The new string is : 1024

```

本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。