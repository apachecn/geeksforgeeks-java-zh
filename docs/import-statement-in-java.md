# Java 导入语句

> 原文:[https://www.geeksforgeeks.org/import-statement-in-java/](https://www.geeksforgeeks.org/import-statement-in-java/)

**在 Java 中导入**语句有助于在单个语句的帮助下获取一个[类](https://www.geeksforgeeks.org/classes-objects-java/)或在一个[包](https://www.geeksforgeeks.org/packages-in-java/)下指定的程序的所有可见类。这是非常有益的，因为程序员不需要编写整个类定义。因此，它提高了程序的可读性。

本文重点介绍 Java 程序中使用的导入语句及其替代方法。

**语法 1:**

```java
import package1[.package2].(*);
```

在这里，

*   **包装 1:** 顶级包装
*   **包装 2:** 包装 1 下的下级包装
*   ***:** 导入所有类

**语法 2:**

```java
import package1[.package2].(myClass);
```

这里，

*   **包装 1:** 顶层包
*   **包装 2:** 顶层包
*   The child package **my class:** only imports myclass.

> **注意:**要么我们可以导入一个类，要么我们可以导入包下指定的所有类。

为了理解为什么我们需要将一个或多个类引入可见性，让我们考虑一个不使用 import 语句的 Java 程序:

**源代码:**

## Java

```java
// Java program to demonstrate the 
// working of a program
// without any import statement

class GFG {

    // Main method
    public static void main(String[] args)
    {
        // Declaring an ArrayList of String type
        ArrayList<String> arrayList
            = new ArrayList<String>();

        // Adding elements in the ArrayList
        arrayList.add("Geeks");
        arrayList.add("For");
        arrayList.add("Geeks");

        // Print the ArrayList
        System.out.println("ArrayList: " + arrayList);
    }
}
```

让我们编译上面的程序:

**编译器判定:**

```java
prog.java:11: error: cannot find symbol
       ArrayList<String> arrayList
       ^
 symbol:   class ArrayList
 location: class GFG

prog.java:12: error: cannot find symbol
           = new ArrayList<String>();
                 ^
 symbol:   class ArrayList
 location: class GFG

2 errors
```

**编译描述:**我们得到编译时错误。Javac 编译器在程序中找不到[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/) 类。ArrayList 类是 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包**的一部分。**所以我们需要在程序中包含 Java.util 包下定义的 ArrayList 类。

***以下三种方式引用一个包下指定的一个外部类或所有外部类:***

### **1。全限定名:**

import 语句是可选的，我们可以使用类的完全限定名来引用程序中的类或包。这个方法告诉编译器这个类是在一个特定的包下定义的，我们希望在我们的程序中使用这个类。每次我们想要使用类中定义的数据成员或成员函数时，我们都需要使用完全限定的名称来引用它。它增加了我们程序的代码大小，因此可读性更差。这是这种方法唯一的缺点。

***示例** :* 下面是在 Java.util 包下定义的类 ArrayList 使用全限定名的实现:

## Java

```java
// Java program to demonstrate the working of a program
// using fully-qualified name or without the use of import
// statement

class GFG {

    // Main method
    public static void main(String[] args)
    {
        // Using fully-qualified name
        // Declaring an ArrayList of String type
        java.util.ArrayList<String> arrayList
            = new java.util.ArrayList<String>();

        // Adding elements in the ArrayList
        arrayList.add("Geeks");
        arrayList.add("For");
        arrayList.add("Geeks");

        // Print the ArrayList
        System.out.println("ArrayList: " + arrayList);
    }
}
```

**输出**

### **2。进口声明:**

import 语句告诉编译器一个类或整个包的路径。它不像 C++中的“#”include，它包含了程序中的全部代码。Import 语句告诉编译器，我们希望使用一个或多个在包下定义的类。它比“完全限定名”方法更有帮助，值得推荐，因为它减少了整体代码大小，提高了源代码的可读性。

下面是实现来说明我们如何将一个类导入到我们的程序中:

## Java

```java
// Java program to demonstrate the 
// working of import statement

// Importing ArrayList class specified 
// under java.util package
import java.util.ArrayList;

class GFG {

    // Main method
    public static void main(String[] args)
    {
        // Declaring an ArrayList of String type
        ArrayList<String> arrayList
            = new ArrayList<String>();

        // Adding elements in the ArrayList
        arrayList.add("Geeks");
        arrayList.add("For");
        arrayList.add("Geeks");

        // Print the ArrayList
        System.out.println("ArrayList: " + arrayList);
    }
}
```

**输出**

```java
ArrayList: [Geeks, For, Geeks]
```

下面的实现说明了如何将所有类导入到我们的程序中:

**源代码:**

## Java

```java
// Java program to demonstrate the
// working of import statement

// Importing all classes specified under java.util package
import java.util.*;

class GFG {

    // Static function to print array elements
    public static void print(int array[])
    {

        System.out.print("Array: [ ");

        for (int i = 0; i < 5; i++)
            System.out.print(array[i] + " ");

        System.out.print("]");
    }

    // main method
    public static void main(String[] args)
    {
        // Declaring an ArrayList of String type
        ArrayList<String> arrayList
            = new ArrayList<String>();

        // Adding elements in the ArrayList
        arrayList.add("Geeks");
        arrayList.add("For");
        arrayList.add("Geeks");

        // Declaring an array of integers
        int array[] = { 10, 3, 5, 11, 20 };

        // sort function defined under Arrays class
        Arrays.sort(array);

        // Print the ArrayList
        System.out.println("ArrayList: " + arrayList);

        // Calling print() function
        print(array);
    }
}
```

**输出**

```java
ArrayList: [Geeks, For, Geeks]
Array: [ 3 5 10 11 20 ]
```