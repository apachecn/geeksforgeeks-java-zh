# Java 中数组列表的数组

> 原文:[https://www.geeksforgeeks.org/array-of-arraylist-in-java/](https://www.geeksforgeeks.org/array-of-arraylist-in-java/)

我们经常遇到 2D 阵列，其中阵列的大部分是空的。由于空间是一个巨大的问题，我们尝试不同的方法来减少空间。其中一个解决方案是当我们知道数组中每行的长度时，使用[锯齿状数组](https://www.geeksforgeeks.org/jagged-array-in-java/)，但是当我们不具体知道每行的长度时，问题就出现了。这里我们使用[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)，因为长度未知。
下面是一个演示上述概念的 Java 程序。

```
// Java code to demonstrate the concept of 
// array of ArrayList

import java.util.*;
public class Arraylist {
    public static void main(String[] args)
    {
        int n = 5;

        // Here al is an array of arraylist having
        // n number of rows.The number of columns on
        // each row depends on the user.
        // al[i].size() will give the size of the
        // i'th row
        ArrayList<Integer>[] al = new ArrayList[n];

        // initializing
        for (int i = 0; i < n; i++) {
            al[i] = new ArrayList<Integer>();
        }

        // We can add any number of columns to each
        // rows as per our wish
        al[0].add(1);
        al[0].add(2);
        al[1].add(5);
        al[2].add(10);
        al[2].add(20);
        al[2].add(30);
        al[3].add(56);
        al[4].add(34);
        al[4].add(67);
        al[4].add(89);
        al[4].add(12);

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < al[i].size(); j++) {
                System.out.print(al[i].get(j) + " ");
            }
            System.out.println();
        }
    }
}
```

输出:

```
1 2 
5 
10 20 30 
56 
34 67 89 12 

```

上面的代码工作正常，但是显示了下面的警告。

```
prog.java:15: warning: [unchecked] unchecked conversion
        ArrayList[] al = new ArrayList[n];
                                  ^
  required: ArrayList[]
  found:    ArrayList[]
1 warning

```

警告基本上是由于线下。

```
ArrayList<Integer>[] al = new ArrayList[n];
```

**如何修复以上警告？**
我们不能在没有警告的情况下使用数组列表数组。我们基本上需要使用数组列表的[数组列表。](https://www.geeksforgeeks.org/arraylist-of-arraylist-in-java/)