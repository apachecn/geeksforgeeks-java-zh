# Java 中的数组声明(单个和多维)

> 原文:[https://www . geesforgeks . org/array-declarations-Java-single-多维/](https://www.geeksforgeeks.org/array-declarations-java-single-multidimensional/)

[Java 中的数组|简介](https://www.geeksforgeeks.org/arrays-in-java/)

**一维数组:**

它是由一个通用名称使用的同类型变量的集合。

示例:
变量的一维数组声明:

```java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        int[] a; // valid declaration
        int b[]; // valid declaration
        int[] c; // valid declaration
    }
}
```

我们可以用任何方式写它。

现在，如果您像下面这样声明数组:

```java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // invalid declaration -- If we want to assign 
        // size of array at the declaration time,  it 
        // gives compile time error.
        int a[5];

        // valid declaration
        int b[];
    }
}
```

现在，假设我们想要编写数组变量的多个声明，那么我们可以这样使用它。

```java
import java.io.*;

class GFG { 
    public static void main(String[] args)
    {
        // valid declaration, both arrays are
        // one dimensional array.
        int a[], b[];

        // invalid declaration
        int c[], [] d;

        // invalid declaration
        int[] e, [] f;
    }
}
```

当我们同时声明多个变量时，我们必须先写变量，然后声明除第一个变量声明之外的那个变量。第一个变量没有限制。

现在，当我们创建数组时，必须传递数组的大小；否则我们会得到编译时错误。
可以使用新运算符创建数组。

```java
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // invalid, here size of array is not given
        int[] a = new int[];

        // valid, here creating 'b' array of size 5
        int[] b = new int[5];

        // valid
        int[] c = new int[0];

        // gives runtime error
        int[] d = new int[-1];
    }
}
```

**打印阵列:**

```java
/* A complete Java program to demonstrate working
   of one dimensional arrays */
class oneDimensionalArray {

    public static void main(String args[])
    {
        int[] a; // one dimensional array declaration
        a = new int[3]; // creating array of size 3
        for (int i = 0; i < 3; i++) {
            a[i] = 100;
            System.out.println(a[i]);
        }
    }
}
```

输出:

```java
100
100
100

```

**二维阵列**

假设，您想要创建 int 类型数据的二维数组。因此，您可以通过以下多种方式声明二维数组:

```java
// Java program to demonstrate different ways
// to create two dimensional array.
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        int a[][]; // valid
        int[][] b; // valid
        int[][] c; // valid
        int[] d[]; // valid
        int[][] e; // valid
        int[] f[]; // valid
        [][] int g; // invalid
        [] int[] h; // invalid
    }
}
```

现在，假设我们想要编写数组变量的多个声明，那么您可以这样使用它。

```java
// Java program to demonstrate multiple declarations
// of array variable
import java.io.*;

class GFG {
public static void main(String[] args)
    {
        // Here, 'a' is two dimensional array, 'b'
        // is two dimensional array
        int[] a[], b[];

        // Here, 'c' is two dimensional array, 'd'
        // is two dimensional array 
        int[] c[], d[]; 

        // Here, 'e' is two dimensional array, 'f' 
        // is three dimensional array
        int[][] e, f[]; 

        // Here, 'g' is two dimensional array, 
        // 'h' is one dimensional array
        int[] g[], h; 
    }
}
```

**在没有新操作符的情况下创建一维数组和二维数组:**

```java
/* Java program for one and two dimensional arrays.
   without new operator*/
class oneTwoDimensionalArray {

     public static void main(String args[])
    {
        int[] a[] = { { 1, 1, 1 }, { 2, 2, 2 },
                     { 3, 3, 3 } }, b = { 20 };

        // print 1D array
        System.out.println(b[0]);

        // print 2D array
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                a[i][j] = 100;
                System.out.println(a[i][j]);
            }
        }
    }
}
```

输出:

```java
20
100
100
100
100
100
100
100
100
100

```

 **使用新运算符创建一维数组和二维数组:**

```java
/* Java program for one and two dimensional arrays.
   using new operator*/
class oneTwoDimensionalArray {

    public static void main(String args[])
    {
        int[] a[], b = { 20 };
        a = new int[3][3];
        b = new int[3];

        // print 1D array
        for (int i = 0; i < 3; i++)
            System.out.println(b[i]);

        // print 2D array
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                a[i][j] = 100;
                System.out.println(a[i][j]);
            }
        }
    }
}
```

输出:

```java
0
0
0
100
100
100
100
100
100
100
100
100

```

本文由**闪烁帕特尔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。