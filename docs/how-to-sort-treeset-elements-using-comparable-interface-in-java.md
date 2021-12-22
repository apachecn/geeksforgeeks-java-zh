# 如何在 Java 中使用可比接口对 TreeSet 元素进行排序？

> 原文:[https://www . geeksforgeeks . org/如何使用 java 中的可比接口对 treeset 元素进行排序/](https://www.geeksforgeeks.org/how-to-sort-treeset-elements-using-comparable-interface-in-java/)

[**TreeSet**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 是 Java 中 [SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 接口的一个实现，使用一个 Tree 进行存储。无论是否提供明确的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)，元件的顺序都由[设置](https://www.geeksforgeeks.org/hashset-in-java/)使用它们的自然顺序来维护。

要使用 java 中的[](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)**可比接口对 TreeSet 元素进行排序，首先，我们创建一个实现可比接口的类 Student。在这个类中，我们覆盖了 [**compareTo()**](https://www.geeksforgeeks.org/java-lang-string-compareto/) 方法。**

****伪码:****

```
// Student class implements comparable interface

class Student implements Comparable<Student> {
    Integer marks;

    Student(Integer marks) {
        this.marks = marks;
    }

    // override toString method
    public String toString() {
        return (" " + this.marks);
    }

    // Override compareTo method to sort LinkedHashSet in ascending order
    public int compareTo(Student stu) {
        return this.marks.compareTo(stu.marks);
    }
}
```

****以下是上述方法的实现:****

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program to demonstrate how to Sort TreeSet using
// Comparable interface in ascending order

import java.util.*;

// Student class implements comparable interface
class Student implements Comparable<Student> {

    Integer marks;

    Student(Integer marks) { this.marks = marks; }

    // override toString method
    public String toString() { return (" " + this.marks); }

    // Override compareTo method to sort TreeSet in
    // ascending order
    public int compareTo(Student stu)
    {
        return this.marks.compareTo(stu.marks);
    }
}

class GFG {
    public static void main(String[] args)
    {

        // New TreeSet
        TreeSet<Student> set = new TreeSet<>();

        // Adding elements to the set
        set.add(new Student(500));
        set.add(new Student(300));
        set.add(new Student(400));
        set.add(new Student(100));
        set.add(new Student(200));

        // Print TreeSet sorted in ascending order
        System.out.println("Sort elements in ascending order : " + set);

    }
}
```

****Output**

```
Sort elements in ascending order : [ 100,  200,  300,  400,  500]
```** 

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Java program demonstrate how to Sort TreeSet using
// Comparable interface in descending order

import java.util.*;

// Student class implements comparable interface
class Student implements Comparable<Student> {

    Integer marks;

    Student(Integer marks) { this.marks = marks; }

    // override toString method
    public String toString() { return (" " + this.marks); }

    // Override compareTo method to sort TreeSet in
    // descending order
    public int compareTo(Student stu)
    {
        return stu.marks.compareTo(this.marks);
    }
}

class GFG {
    public static void main(String[] args)
    {

        // New TreeSet
        TreeSet<Student> set = new TreeSet<>();

        // Adding elements to the set
        set.add(new Student(500));
        set.add(new Student(300));
        set.add(new Student(400));
        set.add(new Student(100));
        set.add(new Student(200));

        // Print TreeSet sorted in descending order
        System.out.println("Sort elements in descending order : " + set);

    }
}
```

****Output**

```
Sort elements in descending order : [ 500,  400,  300,  200,  100]
```**