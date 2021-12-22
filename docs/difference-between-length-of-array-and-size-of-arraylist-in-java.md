# Java 中数组长度和数组列表大小的差异

> 原文:[https://www . geeksforgeeks . org/Java 中数组长度和数组列表大小之差/](https://www.geeksforgeeks.org/difference-between-length-of-array-and-size-of-arraylist-in-java/)

**数组**具有长度属性，该属性提供数组或数组对象的长度。它是在阵列初始化期间分配给内存的总空间。数组是静态的，所以当我们创建一个大小为 n 的数组时，会创建 n 个数组类型的块，JVM 会默认初始化每个块。让我们看下图。
T3】

另一方面，java **数组列表**没有长度属性。java ArrayList 具有 ArrayList 的 size()方法，该方法提供集合中可用对象的总数。

> 我们使用 length 属性来查找 Java 中[数组的长度](https://www.geeksforgeeks.org/arrays-in-java/)和 size()来查找[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)的大小。

下面是上述想法的实现:

```
// Java code to illustrate the difference between
// length in java Array and size in ArrayList

import java.util.ArrayList;

public class GFG {
    // main method
    public static void main(String[] args)
    {

        /* creating an array A[] for 10 elements */
        String A[] = new String[10];

        /* store 2 elements */
        A[0] = "Hello";
        A[1] = "Geeks!";

        /* print length of array A[] */
        System.out.println(A.length); // 10

        /* Creating an ArrayList */
        ArrayList<String> al = new ArrayList<String>();

        /* add 3 elements */
        al.add("G");
        al.add("F");
        al.add("G");

        /* print size of ArrayList */
        System.out.println(al.size()); // 3
    }
}
```

**Output:**

```
10
3

```