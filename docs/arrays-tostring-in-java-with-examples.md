# Java 中的 Arrays.toString()，示例

> 原文:[https://www . geesforgeks . org/arrays-tostring-in-Java-with-examples/](https://www.geeksforgeeks.org/arrays-tostring-in-java-with-examples/)

今天我们将讨论在 Java 中将数组打印为字符串的最简单方法:Arrays.toString()方法。

**如何使用 Arrays.toString()方法？**

**描述:**
返回指定数组内容的字符串表示形式。字符串表示形式由包含在方括号(“[]”)中的数组元素列表组成。相邻的元素由字符“，”(逗号后跟空格)分隔。如果为空，则返回“null”。

在对象数组的情况下，如果数组包含其他数组作为元素，它们将通过从对象继承的 Object.toString()方法转换为字符串，该方法描述它们的标识而不是内容。

**变体:**

*   公共静态字符串 toString(布尔[] arr)
*   公共静态字符串 toString(字节[] arr)
*   公共静态字符串 toString(char[] arr)
*   公共静态字符串 toString(双[] arr)
*   公共静态字符串 toString(浮点[] arr)
*   公共静态字符串 toString(int[] arr)
*   公共静态字符串(长[] arr)
*   公共静态字符串到字符串(对象[] arr)
*   公共静态字符串 toString(短[] arr)

**参数:**
arr–要返回其字符串表示的数组

**返回:**
arr 的字符串表示

**用法:**
下面提到的 Java 代码用例子描述了 Arrays 类的 toString()方法的用法:

```
// Java program to demonstrate working of Arrays.toString()
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Let us create different types of arrays and
        // print their contents using Arrays.toString()
        boolean[] boolArr = new boolean[] { true, true, false, true };
        byte[] byteArr = new byte[] { 10, 20, 30 };
        char[] charArr = new char[] { 'g', 'e', 'e', 'k', 's' };
        double[] dblArr = new double[] { 1, 2, 3, 4 };
        float[] floatArr = new float[] { 1, 2, 3, 4 };
        int[] intArr = new int[] { 1, 2, 3, 4 };
        long[] lomgArr = new long[] { 1, 2, 3, 4 };
        Object[] objArr = new Object[] { 1, 2, 3, 4 };
        short[] shortArr = new short[] { 1, 2, 3, 4 };

        System.out.println(Arrays.toString(boolArr));
        System.out.println(Arrays.toString(byteArr));
        System.out.println(Arrays.toString(charArr));
        System.out.println(Arrays.toString(dblArr));
        System.out.println(Arrays.toString(floatArr));
        System.out.println(Arrays.toString(intArr));
        System.out.println(Arrays.toString(lomgArr));
        System.out.println(Arrays.toString(objArr));
        System.out.println(Arrays.toString(shortArr));
    }
}
```

输出:

```
[true, true, false, true]
[10, 20, 30]
[g, e, e, k, s]
[1.0, 2.0, 3.0, 4.0]
[1.0, 2.0, 3.0, 4.0]
[1, 2, 3, 4]
[1, 2, 3, 4]
[1, 2, 3, 4]
[1, 2, 3, 4]

```

**我们还可以对用户定义类的对象使用 Arrays.toString()。**
由于 Arrays.toString()对于[对象类](https://www.geeksforgeeks.org/object-class-in-java/)的数组是重载的(存在一个方法 Arrays.toString(Object []))，而 Object 是所有类的祖先，所以我们可以对任何类型的对象的数组使用 call。

```
// Java program to demonstrate working of Arrays.toString()
// for user defined objects.
import java.lang.*;
import java.util.*;

// Driver class
class Main {
    public static void main(String[] args)
    {
        Student[] arr = { new Student(111, "bbbb", "london"),
                          new Student(131, "aaaa", "nyc"),
                          new Student(121, "cccc", "jaipur") };

        System.out.println(Arrays.toString(arr));
    }
}

// A class to represent a student.
class Student {
    int rollno;
    String name, address;

    // Constructor
    public Student(int rollno, String name,
                   String address)
    {
        this.rollno = rollno;
        this.name = name;
        this.address = address;
    }

    // Used to print student details in main()
    @override
    public String toString()
    {
        return this.rollno + " " + this.name + " " + this.address;
    }
}
```

输出:

```
[111 bbbb london, 131 aaaa nyc, 121 cccc jaipur]

```

**为什么 [Object.toString()](https://www.geeksforgeeks.org/object-class-in-java/) 不适用于数组？**
在数组上使用 toString()方法可能不起作用。它将数组视为典型对象，并返回默认字符串，即代表数组的“[”，后跟代表数组原始数据类型的字符，后跟标识十六进制代码[详见[本](https://www.geeksforgeeks.org/overriding-tostring-method-in-java/)

本文由 **Shikhar Goel** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。