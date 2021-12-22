# Java . lang . string . compare to()

> 原文:[https://www.geeksforgeeks.org/java-lang-string-compareto/](https://www.geeksforgeeks.org/java-lang-string-compareto/)

**【比较】()**法有三个**变型。本文对它们的描述如下
**1。int compareTo(对象对象)** **:** 这个方法将这个字符串与另一个对象进行比较。**

```
Syntax : 
int compareTo(Object obj)
Parameters : 
obj : the Object to be compared.
Return Value : 
The value 0 if the argument is a string lexicographically equal to this string;
a value less than 0 if the argument is a string lexicographically greater than this string;
and a value greater than 0 if the argument is a string lexicographically less than this string.

```

```
// Java code to demonstrate the
// working of compareTo()
public class Cmp1 {
public static void main(String args[])
    {

        // Initializing Strings
        String str1 = "geeksforgeeks";
        String str2 = new String("geeksforgeeks");
        String str3 = new String("astha");

        // Checking if geeksforgeeks string
        // equates to geeksforgeeks object
        System.out.print("Difference of geeksforgeeks(obj) and geeksforgeeks(str) : ");
        System.out.println(str1.compareTo(str2));

        // Checking if geeksforgeeks string
        // equates to astha object
        System.out.print("Difference of astha(obj) and geeksforgeeks(str) : ");
        System.out.println(str1.compareTo(str3));
    }
}
```

输出:

```
Difference of geeksforgeeks(obj) and geeksforgeeks(str) : 0
Difference of astha(obj) and geeksforgeeks(str) : 6

```

**2。int compare to(String other String)**:这个方法按照字典顺序比较两个字符串。

```
Syntax : 
int compareTo(String anotherString)
Parameters : 
anotherString :  the String to be compared.
Return Value :  
The value 0 if the argument is a string lexicographically equal to this string;
a value less than 0 if the argument is a string lexicographically greater than this string; 
and a value greater than 0 if the argument is a string lexicographically less than this string.

```

```
// Java code to demonstrate the
// working of compareTo()
public class Cmp2 {
public static void main(String args[])
    {

        // Initializing Strings
        String str1 = "geeksforgeeks";
        String str2 = "geeksforgeeks";
        String str3 = "astha";

        // Checking if geeksforgeeks string
        // equates to geeksforgeeks string
        System.out.print("Difference of geeksforgeeks(str) and geeksforgeeks(str) : ");
        System.out.println(str1.compareTo(str2));

        // Checking if geeksforgeeks string
        // equates to astha string
        System.out.print("Difference of astha(str) and geeksforgeeks(str) : ");
        System.out.println(str1.compareTo(str3));
    }
}
```

输出:

```
Difference of geeksforgeeks(str) and geeksforgeeks(str) : 0
Difference of astha(str) and geeksforgeeks(str) : 6

```

**3。int compareToIgnoreCase(String str):**此方法按字典顺序比较两个字符串，忽略大小写差异。

```
Syntax :
int compareToIgnoreCase(String str)
Parameters : 
str : the String to be compared.
Return Value : 
This method returns a negative integer, zero, or a positive integer as
the specified String is greater than, equal to, or less than this String,
ignoring case considerations.

```

```
// Java code to demonstrate the
// working of compareToIgnoreCase()
public class Cmp3 {
public static void main(String args[])
    {

        // Initializing Strings
        String str1 = "geeks";
        String str2 = "gEEkS";

        // Checking if geeksforgeeks string
        // equates to geeksforgeeks string
        // case sensitive
        System.out.print("Difference of geeks and gEEkS (case sensitive) : ");
        System.out.println(str1.compareTo(str2));

        // Checking if geeksforgeeks string
        // equates to astha string
        // case insensitive
        // using compareToIgnoreCase()
        System.out.print("Difference of geeks and gEEkS (case insensitive)  : ");
        System.out.println(str1.compareToIgnoreCase(str2));
    }
}
```

输出:

```
Difference of geeks and gEEkS (case sensitive) : 32
Difference of geeks and gEEkS (case insensitive)  : 0

```

本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上述话题的信息，请写评论