# 如何避免 Java 中 TreeSet 中重复的用户定义对象？

> 原文:[https://www . geesforgeks . org/如何避免重复-用户定义的对象-in-treeset-in-java/](https://www.geeksforgeeks.org/how-to-avoid-duplicate-user-defined-objects-in-treeset-in-java/)

Java 中的 [TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 类是实现[导航集接口](https://www.geeksforgeeks.org/navigableset-java-examples/)的 Java 集合框架的一部分，该接口提供了在排序集中导航的功能。导航集进一步扩展了[排序集界面](https://www.geeksforgeeks.org/sortedset-java-examples/)，该界面提供了保持元素排序的功能。

由于 TreeSet 类实现了一个导航集接口，所以它同时具有导航集和排序集的特性。

TreeSet 根据自然顺序对元素进行排序。所有的包装类和字符串类都已经实现了可比较的接口。但是在自定义对象的情况下，必须在相应的类中实现 Comparable 或 Comparator 接口，这样 TreeSet 就可以按照我们的要求对对象进行排序。

**带有用户定义对象的树集**

当且仅当相应的类实现了 compatible 或 Comparator 接口时，对象才被称为是可比较的。Comparator 接口的 compare()方法和 comparative 接口的 compareTo()方法为 TreeSet 提供了排序逻辑，从而使 TreeSet 能够相应地插入值。*现在，如果你想避免 TreeSet 中对象的任何重复条目，你必须用等式验证* **来实现这些接口。**我们可以通过多种方式做到这一点，

**示例:**

**1。使用可比较的界面:**让我们创建一个学生类，student，它包括学生姓名和学生在任何课程中的排名。在这里，不超过一个学生可以有相同的排名。所以，如果任何一个学生的成绩被另一个学生占据，那么这个成绩就是重复的。否则，学生将根据其姓名按升序排序。

重写 compareTo()方法以提供排序逻辑。在 Comparable 接口的 compareTo()方法中，我们首先检查两个学生对象的排名是否相同，如果相同，则返回 0，表示两个对象相同。否则，如果排名不同，比较学生对象的名称，并相应地返回 1 或-1。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Avoid Duplicate User
// Defined Objects in TreeSet
import java.util.*;

// implementing comparable interface
public class Student implements Comparable<Student> {

    private String name;
    private int rank;

    // constructor
    Student(String name, int rank)
    {
        this.name = name;
        this.rank = rank;
    }

    // returns the student name
    private String getName() { return name; }

    // returns student rank
    public int getRank() { return rank; }

    /*
      overriding compareTo() method.
      if the object has same rank then it is considered as a
      duplicate entry, else, the entry is sorted on the
      basis of the student name.
    */
    @Override public int compareTo(Student o)
    {
        if (rank == o.getRank()) {
            return 0;
        }
        else if (name.compareTo(o.getName()) < 0) {
            return -1;
        }
        else
            return 1;
    }

    // overriding toString() to print the student detail
    @Override public String toString()
    {
        return name + " (" + rank + ")";
    }
}

// driver class
class Gfg {

    public static void main(String args[])
    {

        // create a TreeSet which stores objects of type
        // Student
        TreeSet<Student> students = new TreeSet<>();

        // add objects to the TreeSet
        students.add(new Student("Raghav", 12));
        students.add(new Student("Tilak", 11));

        // adding an object with same rank
        students.add(new Student("Ayush", 12));

        // adding an object with same name but different
        // rank
        students.add(new Student("Raghav", 32));

        // print the TreeSet
        for (Student s : students) {
            System.out.println(s);
        }
    }
}
```

**Output**

```
Raghav (12)
Raghav (32)
Tilak (11)
```

**2。使用比较器界面:**让我们创建一个具有员工姓名和员工 id 的类 Employee。在这里，没有两个或两个以上的员工可以拥有相同的 id。员工是根据他们的身份证分类的。(我们也可以在这个方法中实现与上面相同的逻辑)。使用比较器时，在创建树集时，将比较器的实例传递给树集的构造函数。这确保了 TreeSet 按照我们期望的方式进行排序，而不是按照 TreeSet 使用的自然排序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Avoid Duplicate User
// Defined Objects in TreeSet
import java.util.*;

// implementing comparator interface
public class Employee implements Comparator<Employee> {

    private String name;
    private int id;

    // constructor
    public Employee(String name, int id)
    {
        this.name = name;
        this.id = id;
    }

    // default constructor is required, since we have to
    // pass the instance of Comparator in the constructor,
    // while creating a TreeSet
    public Employee() {}

    // returns employee name
    public String getName() { return name; }

    // returns id of the employee
    public int getId() { return id; }

    /*
     overriding the compare() method, this method compare
     two objects of type Employee on the basis of their id,
     if the ids of two employees is same then its considered
     a duplicate entry. else, it is sorted of the basis of
     id.
    */
    @Override
    public int compare(Employee emp1, Employee emp2)
    {
        if (emp1.getId() == emp2.getId()) {
            return 0;
        }
        else if (emp1.getId() < emp2.getId()) {
            return -1;
        }
        else {
            return 1;
        }
    }

    // overriding toString() to print the employee detail
    @Override public String toString()
    {
        return name + " (" + id + ")";
    }
}
// driver class
class Gfg {
    public static void main(String args[])
    {

        // create a TreeSet which stores objects of type
        // Employee
        TreeSet<Employee> employees
            = new TreeSet<>(new Employee());

        // add objects to the TreeSet
        employees.add(new Employee("Raghav", 934));
        employees.add(new Employee("Tilak", 435));
        employees.add(new Employee("Mumukshi", 252));

        // adding an object with same id
        employees.add(new Employee("Shalu", 934));

        // printing the TreeSet
        for (Employee s : employees) {
            System.out.println(s);
        }
    }
}
```

**Output**

```
Mumukshi (252)
Tilak (435)
Raghav (934)
```