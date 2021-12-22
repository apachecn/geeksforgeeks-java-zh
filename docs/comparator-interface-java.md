# Java 中的比较器接口，示例

> 原文:[https://www.geeksforgeeks.org/comparator-interface-java/](https://www.geeksforgeeks.org/comparator-interface-java/)

比较器接口用于对用户定义类的对象进行排序。比较器对象能够比较同一类的两个对象**。**以下功能比较 obj1 和 obj2。

**语法:**

```java
public int compare(Object obj1, Object obj2):
```

假设我们有一个自己的类类型的 Array/ArrayList，包含 roll no、name、address、DOB 等字段，我们需要根据 Roll no 或 name 对数组进行排序？

**方法 1** :一个显而易见的方法是使用标准算法之一编写我们自己的 sort()函数。此解决方案需要为不同的标准(如卷号和名称)重写整个排序代码。

**方法二:**使用比较器接口——比较器接口用于对用户自定义类的对象进行排序。这个接口存在于 java.util 包中，包含两个比较方法(Object obj1，Object obj2)和 equals(Object 元素)。使用比较器，我们可以根据数据成员对元素进行排序。例如，它可能在卷号、姓名、年龄或其他任何东西上。

用于对列表元素进行排序的 Collections 类的方法用于根据给定的比较器对列表元素进行排序。

```java
public void sort(List list, ComparatorClass c)
```

要对给定的列表进行排序，比较类必须实现一个比较器接口。

### Collections 类的 sort()方法是如何工作的？

在内部，Sort 方法确实会调用它正在排序的类的 Compare 方法。要比较两个元素，它会问“哪个更大？”Compare 方法返回-1、0 或 1 来表示它是否小于、等于或大于另一个。然后，它使用这个结果来确定它们是否应该换成它们的排序。

**示例**

## Java

```java
// Java Program to Demonstrate Working of
// Comparator Interface

// Importing required classes
import java.io.*;
import java.lang.*;
import java.util.*;

// Class 1
// A class to represent a Student
class Student {

    // Attributes of a student
    int rollno;
    String name, address;

    // Constructor
    public Student(int rollno, String name, String address)
    {

        // This keyword regers to current instance itself
        this.rollno = rollno;
        this.name = name;
        this.address = address;
    }

    // Method of Student class
    // To print student details in main()
    public String toString()
    {

        // Returning attributes of Student
        return this.rollno + " " + this.name + " "
            + this.address;
    }
}

// Class 2
// Helper class implementing Comparator interface
class Sortbyroll implements Comparator<Student> {

    // Method
    // Sorting in ascending order of roll number
    public int compare(Student a, Student b)
    {

        return a.rollno - b.rollno;
    }
}

// Class 3
// Helper class implementing Comparator interface
class Sortbyname implements Comparator<Student> {

    // Method
    // Sorting in ascending order of name
    public int compare(Student a, Student b)
    {

        return a.name.compareTo(b.name);
    }
}

// Class 4
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty ArrayList of Student type
        ArrayList<Student> ar = new ArrayList<Student>();

        // Adding entries in above List
        // using add() method
        ar.add(new Student(111, "Mayank", "london"));
        ar.add(new Student(131, "Anshul", "nyc"));
        ar.add(new Student(121, "Solanki", "jaipur"));
        ar.add(new Student(101, "Aggarwal", "Hongkong"));

        // Display message on console for better readibility
        System.out.println("Unsorted");

        // Iterating over entries to print them
        for (int i = 0; i < ar.size(); i++)
            System.out.println(ar.get(i));

        // Sorting student entries by roll number
        Collections.sort(ar, new Sortbyroll());

        // Display message on console for better readibility
        System.out.println("\nSorted by rollno");

        // Again iterating over entries to print them
        for (int i = 0; i < ar.size(); i++)
            System.out.println(ar.get(i));

        // Sorting student entries by name
        Collections.sort(ar, new Sortbyname());

        // Display message on console for better readibility
        System.out.println("\nSorted by name");

        // // Again iterating over entries to print them
        for (int i = 0; i < ar.size(); i++)
            System.out.println(ar.get(i));
    }
}
```

**输出**

```java
Unsorted
111 Mayank london
131 Anshul nyc
121 Solanki jaipur
101 Aggarwal Hongkong

Sorted by rollno
101 Aggarwal Hongkong
111 Mayank london
121 Solanki jaipur
131 Anshul nyc

Sorted by name
101 Aggarwal Hongkong
131 Anshul nyc
111 Mayank london
121 Solanki jaipur
```

通过更改比较方法中的返回值，您可以按照您希望的任何顺序进行排序，例如:对于降序，只需更改上述比较方法中“a”和“b”的位置。

### **按多个字段对集合进行排序**

在前面的例子中，我们已经讨论了如何使用 Comparable 和 Comparator 接口在单个字段的基础上对对象列表进行排序。但是，如果我们要求根据多个字段对 ArrayList 对象进行排序，比如首先根据学生姓名进行排序，其次根据学生年龄进行排序，会怎么样呢？

**示例**

## Java

```java
// Java Program to Demonstrate Working of
// Comparator Interface Via More than One Field

// Importing required classes
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.Iterator;
import java.util.List;

// Class 1
// Helper class representing a Student
class Student {

    // Attributes of student
    String Name;
    int Age;

    // Parameterized constructor
    public Student(String Name, Integer Age)
    {

        // This keyword refers to current instance itself
        this.Name = Name;
        this.Age = Age;
    }

    // Getter setter methods
    public String getName() { return Name; }

    public void setName(String Name) { this.Name = Name; }

    public Integer getAge() { return Age; }

    public void setAge(Integer Age) { this.Age = Age; }

    // Method
    // Overriding toString() method
    @Override public String toString()
    {
        return "Customer{"
            + "Name=" + Name + ", Age=" + Age + '}';
    }

    // Class 2
    // Helper class implementing Comparator interface
    static class CustomerSortingComparator
        implements Comparator<Student> {

        // Method 1
        // To compare customers
        @Override
        public int compare(Student customer1,
                           Student customer2)
        {

            // Comparing customers
            int NameCompare = customer1.getName().compareTo(
                customer2.getName());

            int AgeCompare = customer1.getAge().compareTo(
                customer2.getAge());

            // 2nd level comparison
            return (NameCompare == 0) ? AgeCompare
                                      : NameCompare;
        }
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {

        // Create an empty ArrayList
        // to store Student
        List<Student> al = new ArrayList<>();

        // Create customer objects
        // using constructor initialization
        Student obj1 = new Student("Ajay", 27);
        Student obj2 = new Student("Sneha", 23);
        Student obj3 = new Student("Simran", 37);
        Student obj4 = new Student("Ajay", 22);
        Student obj5 = new Student("Ajay", 29);
        Student obj6 = new Student("Sneha", 22);

        // Adding customer objects to ArrayList
        // using add() method
        al.add(obj1);
        al.add(obj2);
        al.add(obj3);
        al.add(obj4);
        al.add(obj5);
        al.add(obj6);

        // Iterating using Iterator
        // before Sorting ArrayList
        Iterator<Student> custIterator = al.iterator();

        // Display message
        System.out.println("Before Sorting:\n");

        // Holds true till there is single element
        // remaining in List
        while (custIterator.hasNext()) {

            // Iterating using next() method
            System.out.println(custIterator.next());
        }

        // Sorting using sort method of Collections class
        Collections.sort(al,
                         new CustomerSortingComparator());

        // Display message only
        System.out.println("\n\nAfter Sorting:\n");

        // Iterating using enhanced for-loop
        // after Sorting ArrayList
        for (Student customer : al) {
            System.out.println(customer);
        }
    }
}
```

**输出**

```java
Before Sorting:

Customer{Name=Ajay, Age=27}
Customer{Name=Sneha, Age=23}
Customer{Name=Simran, Age=37}
Customer{Name=Ajay, Age=22}
Customer{Name=Ajay, Age=29}
Customer{Name=Sneha, Age=22}

After Sorting:

Customer{Name=Ajay, Age=22}
Customer{Name=Ajay, Age=27}
Customer{Name=Ajay, Age=29}
Customer{Name=Simran, Age=37}
Customer{Name=Sneha, Age=22}
Customer{Name=Sneha, Age=23}
```

本文由**里沙布·马赫塞**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。