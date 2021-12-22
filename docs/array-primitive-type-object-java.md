# 在 Java 中数组是基元类型还是对象？

> 原文:[https://www . geesforgeks . org/array-primitive-type-object-Java/](https://www.geeksforgeeks.org/array-primitive-type-object-java/)

爪哇的一个 **[数组是一个对象](https://www.geeksforgeeks.org/arrays-in-java/)**。现在的问题是这怎么可能？背后的原因是什么？在 Java 中，我们可以使用新的运算符创建数组，我们知道每个对象都是使用新的运算符创建的。因此，我们可以说数组也是一个对象。现在问题也出现了，每次我们为一个类创建一个对象，那么数组的类是什么？

*   在 Java 中，每个数组类型都有一个类，所以 int[]有一个类，float、double 等也有类似的类。
*   数组类型的直接超类是对象。每种数组类型都实现了可克隆和 java.io.Serializable 接口。
*   在 Java 编程语言中，数组是对象( [4.3.1](http://docs.oracle.com/javase/specs/jls/se7/html/jls-4.html#jls-4.3.1) )，是动态创建的，可以分配给 Object ( 4.3.2)类型的变量。对象类的所有方法都可以在数组上调用。

对于每种数组类型，都有相应的类可用，这些类是 java 语言的一部分，程序员不可用。要了解任何数组的类别，我们可以采用以下方法:

```java
// Here x is the name of the array.
System.out.println(x.getClass().getName()); 
```

```java
// Java program to display class of 
// int array type
public class Test
{
    public static void main(String[] args)
    {
        int[] x = new int[3];
        System.out.println(x.getClass().getName());
    }
}
```

输出:

```java
[I 

```

**注意:**【I 这是这个数组的类，一个【(方括号)因为是一维的，I 为整数数据类型。
**下面是为一些数组类型指定相应类名的表格:-**

```java
Array type             Corresponding class Name
int[]                     [I
int[][]                   [[I
double[]                  [D
double[][]                [[D
short[]                   [S
byte[]                    [B
boolean[]                 [Z

```

在 Java 编程语言中，数组是动态创建的对象，可以分配给对象类型的变量。对象类的所有方法都可以在数组上调用。

```java
// Java program to check the class of 
// int array type
public class Test {
    public static void main(String[] args)
    {
        // Object is the parent class of all classes 
        // of Java. Here args is the object of String
        // class.
        System.out.println(args instanceof Object);

        int[] arr = new int[2];

        // Here arr is also an object of int class.
        System.out.println(arr instanceof Object);
    }
}
```

输出:

```java
true
true

```

**参考:**[https://docs . Oracle . com/javase/specs/jls/se7/html/jls-10 . html](https://docs.oracle.com/javase/specs/jls/se7/html/jls-10.html)

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。