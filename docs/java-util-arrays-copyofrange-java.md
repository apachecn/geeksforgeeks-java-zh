# Java 中的 Java.util.Arrays.copyOfRange()

> 原文:[https://www . geesforgeks . org/Java-util-arrays-copy ofrange-Java/](https://www.geeksforgeeks.org/java-util-arrays-copyofrange-java/)

此方法在原始数组的指定范围内创建元素的副本。
**语法:**

```
public static int[] copyOfRange(int[] original_array, int from_index, int to_index) 
```

*   **原始 _ 数组:**要复制的数组
*   **从 _ 索引:**要复制的范围的起始索引
*   **至 _end :** 待复制范围的结束索引

**使用这种方法时需要记住的要点:**

1.  初始索引(即起始索引)必须在 0 到原始数组长度之间
2.  最终索引(即 to_index)可以大于或等于原始数组的长度。如果大于原始数组，则将 0 分配给索引大于或等于原始的副本。
3.  返回数组的长度为从到
4.  这是一种[数组类](https://www.geeksforgeeks.org/array-class-in-java/)的方法

**异常**

*   **arrayindextofboundsexception:**如果初始索引(即 from_index)
    超出了原始数组的范围，则会引发此异常
*   **IllegalArgumentException:**如果 form_index >为 _index，则抛出此异常
*   **NullPointerException :** 如果原始数组为空，将引发此异常

变化:

```
copyOfRange(boolean[] original, int from, int to)
copyOfRange(byte[] original, int from, int to)
copyOfRange(char[] original, int from, int to)
copyOfRange(double[] original, int from, int to)
copyOfRange(float[] original, int from, int to)
copyOfRange(int[] original, int from, int to)
copyOfRange(long[] original, int from, int to)
copyOfRange(short[] original, int from, int to)
copyOfRange(T[] original, int from, int to)
copyOfRange(U[] original, int from, int to, Class newType)
```

让我们通过一个例子来理解这一点:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// copyOfRange method
import java.util.Arrays;
class GFG {
public static void main(String args[])
    {
        int arr[] = { 12, 13, 14, 15, 16, 17, 18 };

        // to index is within the range
        int[] copy = Arrays.copyOfRange(arr, 2, 6);
        for (int i : copy)
            System.out.print(i + "  ");

        System.out.println();
        // to index is out of range
        // It assigns Zero to all the index out of range
        int[] copy1 = Arrays.copyOfRange(arr, 4, arr.length + 3);

        for (int i : copy1)
            System.out.print(i + "  ");

        // It throws IIlegalArgumentException
        // int[] copy2 = Arrays.copyOfRange(arr, 5, 3);

        // It throws ArrayIndexOutOfBoundsException
        // int[] copy2 = Arrays.copyOfRange(arr, 10, arr.length + 5);
    }
}
```

输出:

```
14  15  16  17  
16  17  18  0  0  0  
```

让我们看一个例子**复制范围(T[]原始，int from，int to)和复制范围(U[]原始，int from，int to，Class newType)**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate
// copyOfRange method
import java.util.Arrays;
class GFG {
    // User defined class
    static class Employee {
        int Eid;
        String Ename;

        // constructor
    public Employee(int Eid, String Ename)
        {
            this.Eid = Eid;
            this.Ename = Ename;
        }

        // Override toString()
    public String toString()
        {
            return Eid + "   " + Ename;
        }
    }

    public static void
    main(String args[])
    {
        Employee[] e = { new Employee(10, "geek1"),
                         new Employee(20, "geek2"),
                         new Employee(30, "geek3"),
                         new Employee(40, "geek4"),
                         new Employee(50, "geek5") };

        // Illustration of copyOfRange(T[] original, int from, int to)
        // Working with user defined class
        Employee[] getCopy_Employees = Arrays.copyOfRange(e, 3, 5);
        for (Employee e1 : getCopy_Employees)
            System.out.print(e1.toString() + "  ");

        System.out.println();

        // Illustration of copyOfRange(U[] original, int from, int to, Class newType)
        // In this we store the user defined class Employee into Object class
        // It Throws ArrayStoreException when we try to copy it in a class
        // That is not correct
        Object getcopy[] = Arrays.copyOfRange(e, 1, 3, Object[].class);

        // This throws an error
        // Number getcopy[] = Arrays.copyOfRange(e, 1, 3, Number[].class);

        for (Object e1 : getcopy) {
            System.out.print(e1.toString() + "  ");
        }
    }
}
```

输出:

```
40   geek4  50   geek5  
20   geek2  30   geek3  

```

[**copy of**](https://www.geeksforgeeks.org/java-util-arrays-copyof-java-examples/)**vs copyOfRange**
copy of()从原始数组的第 0 个索引开始复制，并复制指定数量的元素
，而 copy of range()可以从原始数组复制元素的范围。
**参考:**
[docs . Oracle . com/javase/8/docs/API/Java/util/arrays . html # copy ofrange-int:A-int-int-](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html#copyOfRange-int:A-int-int-)
本文由 **Sumit Ghosh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。