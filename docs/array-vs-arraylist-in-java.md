# Java 中的数组 vs 数组列表

> 原文:[https://www.geeksforgeeks.org/array-vs-arraylist-in-java/](https://www.geeksforgeeks.org/array-vs-arraylist-in-java/)

让我们在标题中简单地讨论一下**数组**和**数组列表**的概念，以便将 java 程序中的理解融入到它们之间的决定性差异中。众所周知，数组是线性数据结构，提供了在内存地址空间中以连续方式添加元素的功能，而数组列表是属于集合框架的一个类。作为一名优秀的程序员，尽管知道数组和数组之间的区别，但已经知道在数组上使用数组列表。现在，即使使用数组列表，也有一个传递应该存储在数组列表中的元素的数据类型的功能，无论它是对象、字符串、整数、双精度、浮点等。

> **注:**作为旁注，Java 中的 ArrayList 可以看作类似于 C++中的[向量](https://www.geeksforgeeks.org/vector-in-cpp-stl/)。

**创建数组的方法**

在 Java 中，以下是创建数组的两种不同方式。

1.  简单的固定大小阵列
2.  动态调整数组大小

```java
int arr[] = new int[10]   
```

**语法:**声明静态数组数组

它可以进一步定义为两种类型:

*   **类型 1** :同时声明和初始化
*   **类型 2:** 声明比初始化元素晚。

**类型 1**

```java
Type array_name [array_size] ;
Type array_name = { Element1, Element2, Element3, Element4,...., ElementN } ;
// It is preferable if we have very limited array elements 
```

**2 型**

```java
int arr [100] ;
// This does means we are declaring a memory block named 'arr' 
// which is containing continuous 100 block associated in it
```

> **注意:** arr(0)返回数组的第一个元素，所以这确实意味着如果我们试图打印出 arr(0)，那么我们将得到 Element1。这是一个非常重要的陈述，当涉及到对数组中内存存储的深入理解时，它是不可展示的。

现在让我们详细讨论数组列表的下一个概念，如下所示

**语法:**声明数组列表

```java
Arraylist<Type> al = new ArrayList<Type> ;
// Here Type is the type of elements in ArrayList to be created
```

> **注:**Java 中的 ArrayList(相当于 C++中的 vector)具有动态大小。它可以根据大小缩小或扩大。ArrayList 是集合框架的一部分，存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中。

现在让我们借助数组和数组列表之间的差异来举例说明

**Base 1:** 数组是 Java 提供的基本功能。ArrayList 是 Java 中集合框架的一部分。因此，数组成员是使用[]，而数组列表有一组方法来访问和修改元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate differences between
// Array and ArrayList

// Importing required classes
import java.util.ArrayList;
import java.util.Arrays;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Input array
        int[] arr = new int[2];
        arr[0] = 1;
        arr[1] = 2;

        // Printing first element of array
        System.out.println(arr[0]);

        // ArrayList
        // Creating an arrayList with initial capacity
        // say bi it 2
        ArrayList<Integer> arrL = new ArrayList<Integer>(2);

        // Adding elements to ArrayList
        // using add() method
        arrL.add(1);
        arrL.add(2);

        // Printing alongside accessing
        // elements of ArrayList
        System.out.println(arrL.get(0));
    }
}
```

**Output**

```java
1
1
```

**Base 2:** 数组是固定大小的数据结构，而 ArrayList 不是。在创建对象时，不必提及数组列表的大小。即使我们指定了一些初始容量，我们也可以添加更多的元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate differences between
// Array and ArrayList

// Importing required classes
import java.util.ArrayList;
import java.util.Arrays;

// Main class
class GFG {
    // Main driver method
    public static void main(String args[])
    {
        // Normal Array
        // Need to specify the size for array
        int[] arr = new int[3];
        arr[0] = 1;
        arr[1] = 2;
        arr[2] = 3;

        // We cannot add more elements to array arr[]

        // ArrayList
        // Need not to specify size

        // Declaring an Arraylist of Integer type
        ArrayList<Integer> arrL = new ArrayList<Integer>();

        // Adding elements to ArrayList object
        arrL.add(1);
        arrL.add(2);
        arrL.add(3);
        arrL.add(4);

        // We can add more elements to arrL

        // Print and display Arraylist elements
        System.out.println(arrL);
        // Print and display array elements
        System.out.println(Arrays.toString(arr));
    }
}
```

**Output**

```java
[1, 2, 3, 4]
[1, 2, 3]
```

**Base 3:** 根据数组的定义，数组既可以包含基元数据类型，也可以包含类的对象。但是，数组列表只支持对象条目，不支持基本数据类型。

> **注意:**当我们做 arraylist.add(1)的时候，它会把原始的 int 数据类型转换成 Integer 对象，如下例所示

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.util.ArrayList;
class Test
{
    public static void main(String args[])
    {
       // allowed
        int[] array = new int[3];

        // allowed, however, need to be initialized
        Test[] array1 = new Test[3];

        // not allowed (Uncommenting below line causes
        // compiler error)
        // ArrayList<char> arrL = new ArrayList<char>();

        // Allowed
        ArrayList<Integer> arrL1 = new ArrayList<>();
        ArrayList<String> arrL2 = new ArrayList<>();
        ArrayList<Object> arrL3 = new ArrayList<>();

        System.out.println("Successfully compiled and executed");
    }
}
```

**Output**

```java
Successfully compiled and executed
```

**Base 4:** 由于不能为基元数据类型创建数组列表，数组列表的成员总是对不同内存位置的对象的引用(详见[本](https://www.geeksforgeeks.org/g-fact-46/))。因此，在数组列表中，实际的对象从不存储在连续的位置。实际对象的引用存储在连续的位置。

另一方面，在数组中，它取决于数组是基元类型还是对象类型。在基元类型的情况下，实际值是连续的位置，但是在对象的情况下，分配类似于数组列表。Java ArrayList 支持很多额外的操作，比如 indexOf()， [remove()](https://www.geeksforgeeks.org/arraylist-linkedlist-remove-methods-java-examples/) 等。数组不支持这些功能。

我们已经实现并从输出中看到了它们之间的差异。现在让我们以表格的形式画出结论性的差异来总结这篇文章，如下所示:

<figure class="table">

| [Basic] | array | Array list |
| --- | --- | --- |
| dimension | It can be one-dimensional or multidimensional. | It can only be one-dimensional |
| Traversing element | And For each For is generally used for | The size () method is used to calculate the size of the array list. |
| measure | It is static and has a fixed length. | It is dynamic and can be increased or decreased in size when necessary. |
|  | Faster. The fixed size as shown above. | The speed is relatively slow because of its dynamic nature. |
| Raw data type storage | Raw data types can directly store unlikely objects. | Raw data types are not unlikely arrays added directly, but automatic boxing and unboxing. |
| Indirect added |
| Add element | Assignment operators serve the purpose only. | A special method called add () method is used here. |

</figure>

本文由**普拉哈尔·马图尔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论