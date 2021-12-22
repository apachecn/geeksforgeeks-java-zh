# 如何在 java 中使用 TreeMap 的同时修复 java.lang.ClassCastException？

> 原文:[https://www . geesforgeks . org/how-fix-Java-lang-class castexception-while-use-tree map-in-Java/](https://www.geeksforgeeks.org/how-to-fix-java-lang-classcastexception-while-using-the-treemap-in-java/)

java . lang . class castexception 是 Java 中**未检查的异常**之一。当我们试图将**的一个类类型**的对象转换为**的另一个类类型**的对象时，可能会出现这种情况。

当我们在 TreeMap 中使用自定义类对象作为键，并且既没有实现 [**可比接口**](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/) 也没有实现 [**比较器接口**](https://www.geeksforgeeks.org/comparator-interface-java/) 时，那么 java.lang.ClassCastException 就出现了。

所以有**两种方式**来修复 java.lang.ClassCastException 同时使用 java 中的 tree map:

*   Use [**to compare**](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)
*   Use [**comparator**](https://www.geeksforgeeks.org/comparator-interface-java/)

**方法一:使用** [**可比**](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)

我们可以通过用作实现 Comparable 接口的 TreeMap 的键的对象来修复 java.lang.ClassCastException。

**伪代码:**

```java
// Custom class Student implements comparable interface

class Student implements Comparable<Student> {

  String name;
  Integer marks;

  public Student(String name, Integer marks) {
    this.name = name;
    this.marks = marks;
  }

  // Override toString method
  public String toString() {
    return this.name + " : " + this.marks;
  }

  public int getMarks() {
    return this.marks;
  }

  // Override compareTo method that sort treemap in the ascending order of the marks
  public int compareTo(Student stu) {
    return this.getMarks() - stu.getMarks();
  }
}
```

**实现:**

T5】Java

```java
// Java program to demonstrate how to fix
// java.lang.ClassCastException while using the TreeMap

import java.util.*;

// Custom class Student implements comparable interface
class Student implements Comparable<Student> {

    String name;
    Integer marks;

    public Student(String name, Integer marks)
    {
        this.name = name;
        this.marks = marks;
    }

    // Override toString method
    public String toString()
    {
        return this.name + " : " + this.marks;
    }

    public int getMarks() { return this.marks; }

    // Override compareTo method that sort treemap in the
    // ascending order of the marks
    public int compareTo(Student stu)
    {
        return this.getMarks() - stu.getMarks();
    }
}

public class GFG {
    public static void main(String[] args)
    {

        // New TreeMap
        TreeMap<Student, Integer> map = new TreeMap<>();

        map.put(new Student("Akshay", 500), 1);
        map.put(new Student("Bhanu", 600), 2);
        map.put(new Student("Chetan", 300), 3);

        System.out.println("The Treemap : " + map);
    }
}
```

**输出**

```java
The Treemap : {Chetan : 300=3, Akshay : 500=1, Bhanu : 600=2}
```

**方法二:使用** [**比较仪**](https://www.geeksforgeeks.org/comparator-interface-java/)

我们可以通过在创建 TreeMap 时向构造函数提供一个自定义比较器来修复 java.lang.ClassCastException。

**伪代码:**

```java
// Custom comparator

class MyComparator implements Comparator<Student> {
  // Compare method that sort TreeMap in the ascending order of the marks
  public int compare(Student stu1, Student stu2) {
    return stu1.getMarks() - stu2.getMarks();
  }
}
```

**实现:**

T5】Java

```java
// Java program to demonstrate how to fix
// java.lang.ClassCastException while using the TreeMap

import java.util.*;

// Custom class Student implements comparable interface
class Student {

    String name;
    Integer marks;

    public Student(String name, Integer marks)
    {
        this.name = name;
        this.marks = marks;
    }

    // Override toString method
    public String toString()
    {
        return this.name + " : " + this.marks;
    }

    public int getMarks() { return this.marks; }
}

// Custom comparator
class MyComparator implements Comparator<Student> {

    // Compare method that sort TreeMap in the ascending
    // order of the marks
    public int compare(Student stu1, Student stu2)
    {
        return stu1.getMarks() - stu2.getMarks();
    }
}

public class GFG {
    public static void main(String[] args)
    {

        // New TreeMap
        TreeMap<Student, Integer> map
            = new TreeMap<>(new MyComparator());

        map.put(new Student("Akshay", 500), 1);
        map.put(new Student("Bhanu", 600), 2);
        map.put(new Student("Chetan", 300), 3);

        System.out.println("The Treemap : " + map);
    }
}
```

**输出**

```java
The Treemap : {Chetan : 300=3, Akshay : 500=1, Bhanu : 600=2}
```