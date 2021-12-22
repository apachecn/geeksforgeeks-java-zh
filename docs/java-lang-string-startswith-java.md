# Java 中的 Java . lang . string . start with()

> 原文:[https://www . geesforgeks . org/Java-lang-string-starts with-Java/](https://www.geeksforgeeks.org/java-lang-string-startswith-java/)

startswith()方法有两种**变体。这篇文章大概描绘了他们所有人，如下:
**1。String startsWith() :** 此方法测试字符串是否以从第一个索引开始的指定前缀开始。**

```
**Syntax**
**public boolean startsWith(String prefix)**
**Parameters**
**prefix:** the prefix to be matched.
**Return Value**
It returns true if the character sequence 
represented by the argument is a prefix of the character 
sequence represented by this string; false otherwise. 
```

```
// Java code to demonstrate the
// working of  startsWith()
public class Strt1 {
public static void main(String args[])
    {

        // Initialising String
        String Str = new String("Welcome to geeksforgeeks");

        // Testing the prefix using startsWith()
        System.out.print("Check whether string starts with Welcome : ");
        System.out.println(Str.startsWith("Welcome"));

        // Testing the prefix using startsWith()
        System.out.print("Check whether string starts with geeks : ");
        System.out.println(Str.startsWith("geeks"));
    }
}
```

**输出:**

```
Check whether string starts with Welcome : true
Check whether string starts with geeks : false 
```

****2。字符串开始于(字符串前缀，int strt_pos):** 此变量有两个参数，用于测试字符串是否以指定的前缀开始于指定的索引。**

```
**Syntax**
public boolean startsWith(String prefix, int strt_pos)
**Parameters**
**prefix :** the prefix to be matched.
**strt_pos : ** where to begin looking in the string.
**Return Value**
It returns true if the character sequence
represented by the argument is a prefix of the character
sequence represented by this string; false otherwise. 
```

```
// Java code to demonstrate the
// working of  startsWith()
public class Strt2 {
public static void main(String args[])
    {

        // Initialising String
        String Str = new String("Welcome to geeksforgeeks");

        // Testing the prefix using startsWith()
        System.out.print("Check whether string starts with Welcome at pos 11 : ");
        System.out.println(Str.startsWith("Welcome", 11));

        // Testing the prefix using startsWith()
        System.out.print("Check whether string starts with geeks at pos 11 : ");
        System.out.println(Str.startsWith("geeks", 11));
    }
}
```

**输出:**

```
Check whether string starts with Welcome at pos 11 : false
Check whether string starts with geeks at pos 11 : true 
```

****可能的应用:**该方法主要用于**过滤前缀**，例如，过滤以数字开头的电话号码或以特定字母开头的姓名。后一个在本文中解释。**

```
// Java code to demonstrate the
// application of  startsWith()
public class Appli {
public static void main(String args[])
    {

        // Initialising String
        String Str = new String("Astha Tyagi");

        // Testing the prefix using startsWith()
        System.out.print("Check whether Astha Tyagi starts with A : ");
        System.out.println(Str.startsWith("A"));
    }
}
```

**输出:**

```
Check whether Astha Tyagi starts with A : true 
```

**本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
发现任何不正确的地方请写评论，或者想分享更多关于上面讨论的话题的信息
添加评论折叠**