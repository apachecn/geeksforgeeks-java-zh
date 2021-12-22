# Java 中的 Java.util.Arrays.equals()，示例

> 原文:[https://www . geesforgeks . org/Java-util-arrays-equals-Java-examples/](https://www.geeksforgeeks.org/java-util-arrays-equals-java-examples/)

今天我们将讨论检查两个数组是否相等的最简单方法。如果两个数组包含相同数量的元素，并且两个数组中所有对应的元素对都相等，则认为两个数组相等。换句话说，如果两个数组包含相同顺序的相同元素，则它们是相等的。此外，如果两个数组引用都为 [null](https://www.geeksforgeeks.org/interesting-facts-about-null-in-java/) ，则认为两个数组引用相等。

[Java 中的 Arrays 类](https://www.geeksforgeeks.org/array-class-in-java/)提供方法 *Arrays.equals()* 检查两个数组是否相等。

```
Syntax :
public static boolean equals(int[] a, int[] a2)
Parameters :
a - one array to be tested for equality
a2 - the other array to be tested for equality
Returns : 
true if the two arrays are equal

```

**其他变体:**

*   Public Boolean equals (byte [] a, byte [] a2)
*   Public Boolean equals (short [] a, short [] a2)
*   The static Boolean equals (length [] a, length [] a2)
*   Public Boolean equals (float[] a, float[] a2)
*   Public Boolean equals (double[] a, double[] a2)
*   Public Boolean equals (char[] a, char[] a2)

输出:

```
is arr1 equals to arr2 : true
is arr1 equals to arr3 : false

```

**我们也可以使用 *Arrays.equals()* 来检查用户定义类的对象数组的相等性。看看 *Arrays.equals()* 方法**的最后一个变体

**注意:-** 在对象数组的情况下，必须[覆盖 equals 方法](https://www.geeksforgeeks.org/overriding-equals-method-in-java/)来提供您自己的相等定义，否则您将获得输出取决于 *equals()* 方法对[对象类](https://www.geeksforgeeks.org/object-class-in-java/)的返回。在下面的程序中，我们正在检查学生的 rollno、姓名和地址是否相等。

```
// Java program to demonstrate working of Arrays.equals()
// for user defined objects.

import java.util.Arrays;

public class ArrayEqualDemo
{
    public static void main (String[] args)
    {
        Student [] arr1 = {new Student(111, "bbbb", "london"),
                           new Student(131, "aaaa", "nyc"),
                           new Student(121, "cccc", "jaipur")};

        Student [] arr2 = {new Student(111, "bbbb", "london"),
                           new Student(131, "aaaa", "nyc"),
                           new Student(121, "cccc", "jaipur")};

        Student [] arr3 = {new Student(111, "bbbb", "london"),
                           new Student(121, "dddd", "jaipur"),
                           new Student(131, "aaaa", "nyc"),
                           };

        System.out.println("is arr1 equals to arr2 : " +
                                    Arrays.equals(arr1, arr2));
        System.out.println("is arr1 equals to arr3 : " +
                                    Arrays.equals(arr1, arr3));    
    }    
}

// A class to represent a student.
class Student
{
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

    @Override
    public boolean equals(Object obj) {

        // typecast obj to Student so that we can compare students
        Student s = (Student) obj;

        return this.rollno == s.rollno && this.name.equals(s.name)
                                && this.address.equals(s.address);
    }
}
```

输出:

```
is arr1 equals to arr2 : true
is arr1 equals to arr3 : false

```

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。