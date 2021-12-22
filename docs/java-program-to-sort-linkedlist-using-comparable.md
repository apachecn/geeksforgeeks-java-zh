# 使用可比的

对链接列表进行排序的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到排序-链接列表-使用-可比/](https://www.geeksforgeeks.org/java-program-to-sort-linkedlist-using-comparable/)

在 Java 中，[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)是 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中提供的集合框架的一部分。LinkedList 是一种线性数据结构，其中所有元素在连续的内存位置中没有排序。LinkedList 的优点是它是动态的，并且很容易插入和删除任何元素。我们不能直接访问链表的任何节点，我们需要从头节点开始遍历链表。

Comparable 提供单一的排序顺序。如果我们使用可比，那么它将影响原始类。Comparable Interface 提供了 compareTo()方法来对元素进行排序。在 java 中，java.lang 包提供了类似的功能。我们可以通过调用 Collections.sort(List) 方法对链表进行排序。

**链接列表可以使用 Comparable 按以下顺序排序:**

1.  升序
2.  降序
    *   使用 Collections.reverseOrder()
    *   重写 CompareTo()方法

**类型 1:升序**

要使用 compatible 以升序对链接列表进行排序，我们需要实现类的 compatible 接口，并重写 CompareTo()方法，以针对特定项对链接列表进行排序。之后，我们需要使用 Collection.sort()方法对链表进行排序。

> **语法:**集合.排序(列表对象)

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Sort LinkedList using Comparable
// in ascending order
import java.util.Collections;
import java.util.LinkedList;
import java.util.List;

// User defined class implements Comparable
class Student implements Comparable<Student> {
    String Name;
    int Id;
    int Rank;

    Student(String name, int id, int rank)
    {
        this.Name = name;
        this.Id = id;
        this.Rank = rank;
    }

    // Override the compareTo() method
    @Override public int compareTo(Student s)
    {
        if (Rank > s.Rank) {
            return 1;
        }
        else if (Rank == s.Rank) {
            return 0;
        }
        else {
            return -1;
        }
    }
}

public class Main {
    // Main driver method
    public static void main(String[] args)
    {
        // Create ine LinkedList for Student object
        LinkedList<Student> List
            = new LinkedList<Student>();
        List.add(new Student("Meet", 32, 2));
        List.add(new Student("Jhon", 11, 5));
        List.add(new Student("Sham", 92, 1));
        List.add(new Student("William", 86, 3));
        List.add(new Student("Harry", 35, 4));

        // Print the Unsorted LinkedList
        System.out.println("UnSorted List");
        for (Student s : List) {
            System.out.println(s.Rank + " " + s.Name + " "
                               + s.Id);
        }
        System.out.println();

        // sort in ascending order
        Collections.sort(List);

        // Print the sorted LinkedList
        System.out.println("Sorted List");
        for (Student s : List) {
            // Print the sorted LinkedList
            System.out.println(s.Rank + " " + s.Name + " "
                               + s.Id);
        }
    }
}
```

**Output**

```
UnSorted List
2 Meet 32
5 Jhon 11
1 Sham 92
3 William 86
4 Harry 35

Sorted List
1 Sham 92
2 Meet 32
3 William 86
4 Harry 35
5 Jhon 11
```

**时间复杂度:** O(n log n)

**类型 2:降序**

要按降序对链表进行排序，我们有两种方法。

**A .使用 Collections.reverseOrder()**

在这种方法中，我们必须首先按升序对链接列表进行排序，然后使用 Collections.reverseOrder()我们可以颠倒排序后的链接列表的顺序。

> **语法:** Collections.sort(Listobject，Collections.reverseOrder())

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Sort LinkedList using Comparable in Java
import java.util.Collections;
import java.util.LinkedList;
import java.util.List;

// User defined class implements Comparable
class Student implements Comparable<Student> {
    String Name;
    int Id;
    int Rank;

    Student(String name, int id, int rank)
    {
        this.Name = name;
        this.Id = id;
        this.Rank = rank;
    }

    // Override the compareTo() method
    @Override public int compareTo(Student s)
    {
        if (Rank > s.Rank) {
            return 1;
        }
        else if (Rank == s.Rank) {
            return 0;
        }
        else {
            return -1;
        }
    }
}

public class Main {
    // Main driver method
    public static void main(String[] args)
    {
        // Create ine LinkedList for Student object
        LinkedList<Student> List
            = new LinkedList<Student>();
        List.add(new Student("Meet", 32, 2));
        List.add(new Student("Jhon", 11, 5));
        List.add(new Student("Sham", 92, 1));
        List.add(new Student("William", 86, 3));
        List.add(new Student("Harry", 35, 4));

        // Print the Unsorted LinkedList
        System.out.println("UnSorted List");
        for (Student s : List) {
            System.out.println(s.Rank + " " + s.Name + " "
                               + s.Id);
        }
        System.out.println();

        // sort in descending order
        Collections.sort(List, Collections.reverseOrder());

        // Print the sorted LinkedList
        System.out.println("Sorted List");
        for (Student s : List) {
            // Print the sorted LinkedList
            System.out.println(s.Rank + " " + s.Name + " "
                               + s.Id);
        }
    }
}
```

**Output**

```
UnSorted List
2 Meet 32
5 Jhon 11
1 Sham 92
3 William 86
4 Harry 35

Sorted List
5 Jhon 11
4 Harry 35
3 William 86
2 Meet 32
1 Sham 92
```

**时间复杂度:** O(n log n)

**B .覆盖 CompareTo()方法**

在这种方法中，我们必须重写 compareTo()方法，这样它将按降序返回一个 LinkedList。

*示例:*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Sort LinkedList using Comparable in Java
import java.util.Collections;
import java.util.LinkedList;
import java.util.List;

// User defined class implements Comparable
class Student implements Comparable<Student> {
    String Name;
    int Id;
    int Rank;

    Student(String name, int id, int rank)
    {
        this.Name = name;
        this.Id = id;
        this.Rank = rank;
    }

    // Override the compareTo() method
    @Override public int compareTo(Student s)
    {
        // Changed the Comparison logic
        if (Rank < s.Rank) {
            return 1;
        }
        else if (Rank == s.Rank) {
            return 0;
        }
        else {
            return -1;
        }
    }
}

public class Main {
    // Main driver method
    public static void main(String[] args)
    {
        // Create ine LinkedList for Student object
        LinkedList<Student> List
            = new LinkedList<Student>();
        List.add(new Student("Meet", 32, 2));
        List.add(new Student("Jhon", 11, 5));
        List.add(new Student("Sham", 92, 1));
        List.add(new Student("William", 86, 3));
        List.add(new Student("Harry", 35, 4));

        // Print the Unsorted LinkedList
        System.out.println("UnSorted List");
        for (Student s : List) {
            System.out.println(s.Rank + " " + s.Name + " "
                               + s.Id);
        }
        System.out.println();

        // sort in ascending order
        Collections.sort(List);

        // Print the sorted LinkedList
        System.out.println("Sorted List");
        for (Student s : List) {
            // Print the sorted LinkedList
            System.out.println(s.Rank + " " + s.Name + " "
                               + s.Id);
        }
    }
}
```

**Output**

```
UnSorted List
2 Meet 32
5 Jhon 11
1 Sham 92
3 William 86
4 Harry 35

Sorted List
5 Jhon 11
4 Harry 35
3 William 86
2 Meet 32
1 Sham 92
```

**时间复杂度:** O(n log n)