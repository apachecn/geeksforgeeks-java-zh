# 在 Java 中迭代数组

> 原文:[https://www.geeksforgeeks.org/iterating-arrays-java/](https://www.geeksforgeeks.org/iterating-arrays-java/)

迭代数组意味着逐个访问数组的每个元素。Java 中可能有很多迭代数组的方法，下面是一些简单的方法。

**方法 1:** 使用 for 循环:
这是最简单的方法，我们只需要使用 for 循环，其中计数器变量逐个访问每个元素。

```
// Java program to iterate over an array
// using for loop
import java.io.*;
class GFG {

    public static void main(String args[]) throws IOException
    {
        int ar[] = { 1, 2, 3, 4, 5, 6, 7, 8 };
        int i, x;

        // iterating over an array
        for (i = 0; i < ar.length; i++) {

            // accessing each element of array
            x = ar[i];
            System.out.print(x + " ");
        }
    }
}
```

输出:

```
1 2 3 4 5 6 7 8 

```

**方法 2:** 每个循环使用:
每个循环优化代码，节省打字和时间。

```
// JAVA program to iterate over an array
// using for loop
import java.io.*;
class GFG {

    public static void main(String args[]) throws IOException
    {
        int ar[] = { 1, 2, 3, 4, 5, 6, 7, 8 };
        int x;

        // iterating over an array
        for (int i : ar) {

            // accessing each element of array
            x = i;
            System.out.print(x + " ");
        }
    }
}
```

输出:

```
1 2 3 4 5 6 7 8 

```

本文由**尼基塔·蒂瓦里**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。