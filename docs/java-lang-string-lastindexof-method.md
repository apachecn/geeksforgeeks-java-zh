# Java . lang . string . last indexof()方法

> 原文:[https://www . geesforgeks . org/Java-lang-string-last indexof-method/](https://www.geeksforgeeks.org/java-lang-string-lastindexof-method/)

lastIndexOf()方法有四个**变体。这篇文章大概描绘了他们所有人，如下:
**1。lastIndexOf() :** 此方法**返回字符序列中最后一个**出现字符的索引。******

```java
****Syntax:**
**int lastIndexOf(int ch)**
**Parameters:**
**ch** : a character.
**Return Value:**
This method returns the index.** 
```

```java
**// Java code to demonstrate the
// working of lastIndexOf()
public class L_index1 {

public static void main(String args[])
    {

        // Initialising String
        String Str = new String("Welcome to geeksforgeeks");

        System.out.print("Found Last Index of g at : ");

        // Last index of 'g' will print
        // prints 19
        System.out.println(Str.lastIndexOf('g'));
    }
}**
```

****输出:****

```java
**Found Last Index of g at : 19** 
```

******2。lastIndexOf(int ch，int beg) :** 该方法**返回**该对象表示的字符序列中最后一次出现的小于或等于 beg 的字符的索引，如果该字符在该点之前没有出现，则返回-1。****

```java
****Syntax:**
**public int lastIndexOf(int ch, int beg)**
**Parameters:**
**ch** : a character.
**beg** : the index to start the search from.
**Returned Value:**
This method returns the index.** 
```

```java
**// Java code to demonstrate the
// working of lastIndexOf()
public class L_index2 {

public static void main(String args[])
    {

        // Initialising String
        String Str = new String("Welcome to geeksforgeeks");

        System.out.print("Found Last Index of g at : ");

        // Last index of 'g' before 15 will print
        // prints 11
        System.out.println(Str.lastIndexOf('g', 15));
    }
}**
```

****输出:****

```java
**Found Last Index of g at : 11** 
```

******3。lastIndexOf(String str) :** 该方法接受一个 String 作为参数，如果字符串参数作为子串在该对象中出现一次或多次，则返回该子串最后一个的**的第一个**字符的索引。如果它不作为子字符串出现，则返回-1。********

```java
**Syntax:**
**public int lastIndexOf(String str)**
**Parameters:**
**str** : a string.
**Returned Value:**
This method returns the index. 
```

```java
// Java code to demonstrate the
// working of lastIndexOf(String str)
public class L_index3 {

public static void main(String args[])
    {

        // Initialising String
        String Str = new String("Welcome to geeksforgeeks");

        System.out.print("Found substring geeks at : ");

        // start index of last occurrence of "geeks'
        // prints 19
        System.out.println(Str.lastIndexOf("geeks"));
    }
}
```

**输出:**

```java
Found substring geeks at : 19 
```

****4。lastIndexOf(String str，int beg)** :这个方法**返回**这个字符串中指定子字符串最后一次出现的索引，从指定的索引开始向后搜索。**

```java
**Syntax:**
**public int lastIndexOf(String str, int beg)**
**Parameters**
**beg** : the index to start the search from.
**str** : a string.
**Return Value**
This method returns the index. 
```

```java
// Java code to demonstrate the
// working of lastIndexOf(String str,  int beg)
public class L_index4 {

public static void main(String args[])
    {

        // Initialising String
        String Str = new String("Welcome to geeksforgeeks");

        System.out.print("Found substring geeks at : ");

        // start index of last occurrence of "geeks'
        // before 15
        // prints 11
        System.out.println(Str.lastIndexOf("geeks", 15));
    }
}
```

**输出:**

```java
Found substring geeks at : 11 
```

**本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**