# Java 中的长度 vs 长度()

> 原文:[https://www.geeksforgeeks.org/length-vs-length-java/](https://www.geeksforgeeks.org/length-vs-length-java/)

**数组长度:**长度是适用于[数组](https://www.geeksforgeeks.org/arrays-in-java/)的最终变量。借助长度变量，我们可以得到数组的大小。

**string.length() :** length()方法是适用于字符串对象的最终变量。length()方法返回字符串中的字符数。

**长度 vs 长度()**

1.length 变量适用于数组，但不适用于字符串对象，而 length()方法适用于字符串对象，但不适用于数组。

2.示例:

```
// length can be used for int[], double[], String[] 
// to know the length of the arrays.

// length() can be used for String, StringBuilder, etc 
// String class related Objects to know the length of the String
```

3.要直接访问数组的字段成员，我们可以使用**。长度；**鉴于**。length()** 调用方法来访问字段成员。

示例:

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java program to illustrate the
// concept of length
// and length()
public class Test {
    public static void main(String[] args)
    {
        // Here array is the array name of int type
        int[] array = new int[4];
        System.out.println("The size of the array is "
                           + array.length);

        // Here str is a string object
        String str = "GeeksforGeeks";
        System.out.println("The size of the String is "
                           + str.length());
    }
}
```

**Output**

```
The size of the array is 4
The size of the String is 13
```

**基于长度 vs 长度()概念的练习题**

**我们来看看以下程序的输出:**

*   **下面的程序会输出什么？**

## Java 语言（一种计算机语言，尤用于创建网站）

```
public class Test {
    public static void main(String[] args)
    {
        // Here str is the array name of String type.
        String[] str = { "GEEKS", "FOR", "GEEKS" };
        System.out.println(str.length);
    }
}
```

**Output**

```
3
```

**说明:**这里的字符串是类型字符串的数组，这就是为什么用 str.length 来求它的长度。

*   **下面的程序会输出什么？**

## Java 语言（一种计算机语言，尤用于创建网站）

```
public class Test {
    public static void main(String[] args)
    {
        // Here str[0] pointing to a string i.e. GEEKS
        String[] str = { "GEEKS", "FOR", "GEEKS" };
        System.out.println(str.length());
    }
}
```

**输出:**

```
error: cannot find symbol
symbol: method length()
location: variable str of type String[]
```

**说明:**这里的 str 是类型字符串的数组，这就是为什么 str.length()不能用来求其长度的原因。

*   **下面的程序会输出什么？**

## Java 语言（一种计算机语言，尤用于创建网站）

```
public class Test {
    public static void main(String[] args)
    {
        // Here str[0] pointing to String i.e. GEEKS
        String[] str = { "GEEKS", "FOR", "GEEKS" };
        System.out.println(str[0].length());
    }
}
```

**Output**

```
5
```

**解释:**这里 str[0]指向 String 即 GEEKS，因此可以使用访问。

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。