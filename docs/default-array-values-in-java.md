# Java 中的默认数组值

> 原文:[https://www.geeksforgeeks.org/default-array-values-in-java/](https://www.geeksforgeeks.org/default-array-values-in-java/)

如果我们不对数组元素赋值，并试图访问它们，编译器不会像简单变量那样产生错误[。相反，它分配的值不是垃圾。](https://www.geeksforgeeks.org/g-fact-50/)

以下是默认的赋值。

*   Boolean value: false
*   int:0
*   双倍:0.0
*   字符串：空
*   User defined type: null

```java
// Java program to demonstrate default values of array
// elements
class ArrayDemo
{
    public static void main(String[] args)
    {
        System.out.println("String array default values:");
        String str[] = new String[5];
        for (String s : str)
            System.out.print(s + " ");

        System.out.println("\n\nInteger array default values:");
        int num[] = new int[5];
        for (int val : num)
             System.out.print(val + " ");

        System.out.println("\n\nDouble array default values:");
        double dnum[] = new double[5];
        for (double val : dnum)
            System.out.print(val + " ");

        System.out.println("\n\nBoolean array default values:");
        boolean bnum[] = new boolean[5];
        for (boolean val : bnum)
            System.out.print(val + " ");

        System.out.println("\n\nReference Array default values:");
        ArrayDemo ademo[] = new ArrayDemo[5];
        for (ArrayDemo val : ademo)
            System.out.print(val + " ");
    }
}
```

输出:

```java
String array default values:
null null null null null 

Integer array default values:
0 0 0 0 0 

Double array default values:
0.0 0.0 0.0 0.0 0.0 

Boolean array default values:
false false false false false 

Reference Array default values:
null null null null null 

```

本文由**闪烁泰亚吉**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。