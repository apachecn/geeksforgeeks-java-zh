# 如何在 Java 中使用可比接口对向量元素进行排序？

> 原文:[https://www . geesforgeks . org/如何使用 java 中的可比接口对向量元素进行排序/](https://www.geeksforgeeks.org/how-to-sort-vector-elements-using-comparable-interface-in-java/)

Vector 是集合的子接口。如果我们想把一组单独的对象表示成一个单一的实体，其中允许重复并且插入顺序必须保留，那么我们应该选择向量。它是一个可调整大小或可增长的数组。它实现了一个可序列化、可克隆和可随机访问的接口。向量中的每个方法都是同步的，因此向量对象是线程安全的。

[**【可比界面】**](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/) 用于对自定义类的对象进行排序。这个接口存在于***Java . lang '*****包中，它只包含一个方法 compareTo(对象)。但是它只提供了一个单一的排序序列，也就是说，我们可以根据单个数据成员对元素进行排序。**

*****对比*** **法****

**此方法用于将当前对象与指定对象进行比较，并根据两个对象的比较结果返回三个值。使用可比接口，我们可以对字符串类对象、用户定义的类对象和所有包装器类对象的元素进行排序。**

****语法:****

```
public int compareTo(Object obj); 
```

****返回类型:**整数值**

***   A negative value if and only if the first object must precede the second object.*   Positive value if and only if the first object must be after the second object.*   And is zero only when the first object is equal to the second object.**

****Collections** 是一个存在于 *java.util* 包中的实用程序类，用于定义排序、搜索和反转等收集对象的多种实用方法。**

**为了对列表的元素进行排序，Collections 类定义了如下两种排序方式:**

***   Static void sort (List l): sort according to the default natural sort order. In this case, a list should contain a similar object or comparable object, otherwise we will get a runtime exception, and the list should not contain null values, otherwise we will get a null value exception of [](https://www.geeksforgeeks.org/null-pointer-exception-in-java/).*   Static empty sort (List L, Comparator C): sort according to the custom sort order.**

****实施:****

**考虑创建一个自定义类名 Students，它实现了一个类似的接口，在这个接口中我们可以获得每个学生的 id。在驱动程序类内部，我们创建了一个学生类类型的向量，然后我们可以通过比较学生的 id，使用可比较的接口对向量元素进行排序。**

****例 1:****

## **Java**

```
// Java Program to Sort Vector Elements
// using Comparable Interface

// Importing Collections and Vector classes from
// java.util package
import java.util.*;
import java.util.Collections;
import java.util.Vector;

// Class 1
// Helper class
// Class implementing comparable interface
class Student implements Comparable<Student> {

    // Declaring a variable
    private int id;

    // Initializing the above variable through
    // self constructor of this class
    public Student(int id)
    {

        // 'this' keyword refers to current object itself
        this.id = id;
    }

    // Converting the above Integer variable to String
    public String toString()
    {
        return "Student[" + this.id + "]";
    }

    // Getting the 'id'
    public int getId() { return this.id; }

    // Comparing the ids ot two student
    // using the compareTo() method
    public int compareTo(Student otherStudent)
    {
        return this.getId() - otherStudent.getId();
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of Vector type
        // Declaring object of Student(user-defined type)
        Vector<Student> student = new Vector<>();

        // Adding student id to vector
        // Custom input elements
        student.add(new Student(1));
        student.add(new Student(2));
        student.add(new Student(9));
        student.add(new Student(4));
        student.add(new Student(34));

        // Print all the elements
        // before sorting
        System.out.println(student);

        // Calling sort() method of collections
        Collections.sort(student);

        // Print all the elements
        // after sorting
        System.out.println(student);
    }
}
```

****输出**

```
[Student[1], Student[2], Student[9], Student[4], Student[34]]
[Student[1], Student[2], Student[4], Student[9], Student[34]]
```** 

****示例 2:** 学生姓名、标记和 id，其中我们将根据学生标记**

## **Java**

```
// Java Program to Sort Vector Elements
// using Comparable Interface

// Importing Collection an Vector classes from
// java.util package
import java.util.Collections;
import java.util.Vector;
import java.util.*;

// Class 1
// Helper class
// Class implementing comparable interface
class Student implements Comparable<Student> {

// // Declaring a variables- student name , marks and id
String name;
int marks;
int id;

// Initializing the above variable through
// self constructor of this class
public Student(String name,int marks,int id) {

  // 'this' keyword refers to current object itself 
  this.name=name;
  this.marks=marks;
  this.id=id;
  }

// Getting the 'id'
public int getMarks(){
 return this.marks;
 }

// Comparing the ids ot two student
// using the compareTo() method
public int compareTo(Student otherStudent) {

  return this.getMarks()-otherStudent.getMarks();
  }

}

// Class 2
// Main class
class GFG {

// Main driver method
public static void main(String[] args) {

// Creating an object of Vector type
// Declaring object of Student(user-defined type)
Vector<Student> student= new Vector<>();

// Adding student id to vector
// Custom input elements
student.add(new Student("Roshan",86,1));
student.add(new Student("Ritik",96,2));
student.add(new Student("Ashish",99,4));
student.add(new Student("Sandeep",100,9));
student.add(new Student("Piyush",88,34));

// Iterate over the sorted vector
// using for each loop
// before calling sort() method
for(Student s : student)

// Print and display the sorted vector
System.out.println("Name:"+s.name +"->"+"Marks:"+s.marks+"->"+"ID:"+s.id);

// New line
System.out.println() ;

// Calling sort() method of collections
Collections.sort(student);

// Iterate over the sorted vector
// using for each loop
// after calling sort() method
for(Student s : student)

// Print and display the sorted vector
System.out.println("Name:"+s.name +"->"+"Marks:"+s.marks+"->"+"ID:"+s.id);

}

}
```

****输出**

```
Name:Roshan->Marks:86->ID:1
Name:Ritik->Marks:96->ID:2
Name:Ashish->Marks:99->ID:4
Name:Sandeep->Marks:100->ID:9
Name:Piyush->Marks:88->ID:34

Name:Roshan->Marks:86->ID:1
Name:Piyush->Marks:88->ID:34
Name:Ritik->Marks:96->ID:2
Name:Ashish->Marks:99->ID:4
Name:Sandeep->Marks:100->ID:9
```**