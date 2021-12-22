# Java 中如何使用可比接口对 HashSet 元素进行排序？

> 原文:[https://www . geeksforgeeks . org/how-sort-hashset-elements-使用 java 中的可比接口/](https://www.geeksforgeeks.org/how-to-sort-hashset-elements-using-comparable-interface-in-java/)

[**HashSet**](https://www.geeksforgeeks.org/hashset-in-java/) 类实现了 [Set 接口](https://www.geeksforgeeks.org/set-in-java/)，由哈希表支持，哈希表实际上是一个 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 实例。不能保证集合的迭代顺序，这意味着当我们迭代 HashSet 时，不能保证我们得到的元素是按照它们被插入的顺序。

要使用 java 中的[](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)**可比接口对 HashSet 元素进行排序，首先，我们创建一个实现可比接口的类 Student。在这个类中，我们覆盖了 [**compareTo()**](https://www.geeksforgeeks.org/java-equals-compareto-equalsignorecase-and-compare/) 方法。**

****伪代码:****

```java
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

**然后我们将集合传递给 TreeSet 构造函数来对元素进行排序。**

```java
// TreeSet to sort LinkedHashSet using comparable

TreeSet<Student> tree_set = new TreeSet<>(set);
```

****以下是上述方法的全面实施:****

****例 1:****

## **Java**

```java
// Java program to demonstrate how to Sort HashSet using
// Comparable interface

import java.util.*;

// Student class implements comparable interface
class Student implements Comparable<Student> {

    Integer marks;

    Student(Integer marks) { this.marks = marks; }

    // override toString method
    public String toString() { return (" " + this.marks); }

    // Override compareTo method to sort HashSet in
    // ascending order
    public int compareTo(Student stu)
    {
        return this.marks.compareTo(stu.marks);
    }
}

class GFG {
    public static void main(String[] args)
    {

        // New HashSet
        HashSet<Student> set = new HashSet<>();

        // Adding elements to the set
        set.add(new Student(500));
        set.add(new Student(300));
        set.add(new Student(400));
        set.add(new Student(100));
        set.add(new Student(200));

        // Print Before sort
        System.out.println("Before sort elements in ascending order : "
            + set);

        // TreeSet to sort HashSet using comparable
        // interface
        TreeSet<Student> tree_set = new TreeSet<>(set);

        // Print after sorting
        System.out.println("After sort elements in ascending order : "
            + tree_set);
    }
}
```

****输出**

```java
Before sort elements in ascending order : [ 300,  400,  500,  200,  100]
After sort elements in ascending order : [ 100,  200,  300,  400,  500]
```** 

****例 2:****

## **Java**

```java
// Java program to demonstrate how to Sort HashSet using
// Comparable interface

import java.util.*;

// Student class implements comparable interface
class Student implements Comparable<Student> {

    Integer marks;

    Student(Integer marks) { this.marks = marks; }

    // override toString method
    public String toString() { return (" " + this.marks); }

    // Override compareTo method to sort HashSet in
    // descending order
    public int compareTo(Student stu)
    {
        return stu.marks.compareTo(this.marks);
    }
}

class GFG {
    public static void main(String[] args)
    {

        // New HashSet
        HashSet<Student> set = new HashSet<>();

        // Adding elements to the set
        set.add(new Student(500));
        set.add(new Student(300));
        set.add(new Student(400));
        set.add(new Student(100));
        set.add(new Student(200));

        // Print Before sort
        System.out.println("Before sort elements in descending order : "
            + set);

        // TreeSet to sort HashSet using comparable
        // interface
        TreeSet<Student> tree_set = new TreeSet<>(set);

        // Print after sorting
        System.out.println("After sort elements in descending order : "
            + tree_set);
    }
}
```

****输出**

```java
Before sort elements in descending order : [ 300,  400,  500,  200,  100]
After sort elements in descending order : [ 500,  400,  300,  200,  100]
```**