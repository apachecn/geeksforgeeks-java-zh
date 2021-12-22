# Java 中的数组 copyOf()，示例

> 原文:[https://www . geeksforgeeks . org/arrays-copy of-in-Java-with-examples/](https://www.geeksforgeeks.org/arrays-copyof-in-java-with-examples/)

java.util.Arrays.copyOf()方法在 [java.util.Arrays](https://www.geeksforgeeks.org/array-class-in-java/) 类中。它复制指定的数组，用 false 截断或填充(如有必要)，使副本具有指定的长度。

**语法:**

```
 copyOf(int[] original, int newLength) 
```

*   **原始**–原始阵列
*   **新长度**–原始数组的副本

```
// Java program to illustrate copyof method
import java.util.Arrays;

public class Main
{
    public static void main(String args[])
    {
        // initializing an array original
        int[] org = new int[] {1, 2 ,3};

        System.out.println("Original Array");
        for (int i = 0; i < org.length; i++)
            System.out.print(org[i] + " ");

        // copying array org to copy
        int[] copy = Arrays.copyOf(org, 5);

        // Changing some elements of copy
        copy[3] = 11;
        copy[4] = 55;

        System.out.println("\nNew array copy after modifications:");
        for (int i = 0; i < copy.length; i++)
            System.out.print(copy[i] + " ");
    }
}
```

输出:

```
Original Array
1 2 3 
New array copy after modifications:
1 2 3 11 55 

```

**如果复制数组的长度大于原始数组，会发生什么情况？**
对于原始数组和新数组中有效的所有索引，这两个数组将具有相同的值。
但是，如果复制的数组长度大于原始数组，则原始数组中缺失的索引在副本中将具有**零**。

```
// Java program to illustrate copyOf when new array
// is of higher length.
import java.util.Arrays;

public class Main 
{
  public static void main(String args[]) 
  {
      // initializing an array original
      int[] org = new int[] {1, 2 ,3};

      System.out.println("Original Array : \n");
      for (int i = 0; i < org.length; i++)
           System.out.print(org[i] + " ");  

       // copying array org to copy 
       // Here, new array has 5 elements - two
       // elements more than the original array
       int[] copy = Arrays.copyOf(org, 5);

       System.out.print("\nNew array copy (of higher length):\n");
       for (int i = 0; i < copy.length; i++) 
           System.out.print(copy[i] + " ");
    }
}
```

输出:

```
Original Array : 
1 2 3 
New array copy (of higher length):
1 2 3 0 0 

```

如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。