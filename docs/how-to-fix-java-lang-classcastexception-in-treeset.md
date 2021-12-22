# 如何修复 TreeSet 中的 java.lang.ClassCastException？

> 原文:[https://www . geesforgeks . org/how-fix-Java-lang-class castexception-in-treeset/](https://www.geeksforgeeks.org/how-to-fix-java-lang-classcastexception-in-treeset/)

Java 中的 [TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 类实现了 [Set](https://www.geeksforgeeks.org/set-in-java/) 接口，该接口使用树来存储包含以升序存储的唯一对象的元素。在使用 TreeSet 对象时，您可能会遇到一个名为**的异常。基本上，TreeSet 元素是使用自然排序或使用构造函数中定义的比较器进行排序的。如果两者都没有发生，即自然排序没有发生，也没有提供任何比较器，那么 java 抛出一个异常，即**Java . lang . class castexception**。**

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate ClassCastException by TreeSet

import java.util.TreeSet;

// class which is going to assign
// student marks
class Student {

    int marks;

    // constructor
    public Student(int marks) { this.marks = marks; }

    // override toString() method
    // for display purpose
    public String toString()
    {
        return "Student marks = " + this.marks;
    }
}

// Driver class
class GFG {
    public static void main(String[] args)
    {

        // Declaring Tree Set
        TreeSet<Student> treeSet = new TreeSet<Student>();

        // this line will throw java.lang.ClassCastException
        treeSet.add(new Student(1));

        // Displaying the contents of in treeSet
        System.out.println(treeSet);
    }
}
```

**输出**

> 线程“main”Java . lang . classcastexception 中的异常:类 Student 无法强制转换为类 Java . lang . compatible(Student 位于加载程序“app”的未命名模块中)；Java . lang . compatible 位于加载程序“bootstrap”的 java.base 模块中
> 
> at Java . base/Java . util . treemap . compare(treemap . Java:1291)
> 
> at Java . base/Java . util . treemap . put(treemap . Java:536)
> 
> at Java . base/Java . util . treeset . add(treeset . Java:255)
> 
> 在 GFG.main(文件. java:31)

我们可以通过两种方式解决这个异常:

1.  通过实现**可比**接口
2.  通过定义自定义[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)类

**方法 1(实现可比接口)**

Java Comparable 接口是由一个类实现的，该类用于根据自然顺序对对象进行比较和排序。使用 compareTo()函数可以自然排序。字符串对象和包装器类对象根据内置的 **compareTo()** 函数进行排序。

如果 **compareTo** 函数返回正或负或零，则当前对象分别大于、小于和等于提供的对象。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to sort student data
// according to marks
// using Comparable interface

import java.util.TreeSet;

// class which is going to assign
// student marks
class Student implements Comparable<Student> {

    int id;
    String name;
    int marks;

    // constructor
    public Student(int id, String name, int marks)
    {

        // assigning values
        this.id = id;
        this.name = name;
        this.marks = marks;
    }

    // compareTo method to sort in
    // ascending order
    public int compareTo(Student obj)
    {
        return this.marks - obj.marks;
    }

    // override toString() method
    // for display purpose
    public String toString()
    {
        return "Id: " + this.id + " Name: " + this.name
            + " Marks: " + this.marks;
    }
}

// Driver class
class GFG {
    public static void main(String[] args)
    {

        // Declaring Tree Set
        TreeSet<Student> treeSet = new TreeSet<Student>();

        treeSet.add(new Student(1, "Suresh", 87));
        treeSet.add(new Student(2, "Ramesh", 78));
        treeSet.add(new Student(3, "Lokesh", 95));

        // Displaying the contents of in treeSet
        System.out.println(treeSet);
    }
}
```

**Output**

```
[Id: 2 Name: Ramesh Marks: 78, Id: 1 Name: Suresh Marks: 87, Id: 3 Name: Lokesh Marks: 95]
```

**方法 2(使用自定义比较器类)**

比较器是一个必须由类实现的接口，通过它我们可以对用户定义类的对象进行排序。它有两个广泛使用的主要方法，compare(T o1，T o2)和 equals(Object obj)，后者分别返回一个 int 和一个 boolean。让我们用一个比较器来实现同样的例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to sort student data
// according to marks using custom class
// which implements Comparator

// comparator interface present in
// java.util package
import java.util.*;
// class which is going to assign
// student marks
class Student {

    int id;
    String name;
    int marks;

    // constructor
    public Student(int id, String name, int marks)
    {

        // assigning values
        this.id = id;
        this.name = name;
        this.marks = marks;
    }

    // method to return
    // current marks of student
    public int getMarks() { return this.marks; }

    // override toString() method
    // for display purpose
    public String toString()
    {
        return "Id: " + this.id + " Name: " + this.name
            + " Marks: " + this.marks;
    }
}

// StuComparator class will compare
// objects ans sorts in
// ascending order
class StuComparator implements Comparator<Student> {

    // defining compare method
    public int compare(Student obj1, Student obj2)
    {
        return obj1.getMarks() - obj2.getMarks();
    }
}

// Driver class
class GFG {
    public static void main(String[] args)
    {

        // Declaring Tree Set
        TreeSet<Student> treeSet
            = new TreeSet<Student>(new StuComparator());

        treeSet.add(new Student(1, "Suresh", 87));
        treeSet.add(new Student(2, "Ramesh", 78));
        treeSet.add(new Student(3, "Lokesh", 95));

        // Displaying the contents of in treeSet
        System.out.println(treeSet);
    }
}
```

**Output**

```
[Id: 2 Name: Ramesh Marks: 78, Id: 1 Name: Suresh Marks: 87, Id: 3 Name: Lokesh Marks: 95]
```