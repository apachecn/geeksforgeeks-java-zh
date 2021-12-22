# 使用比较器使用二分搜索法从列表中搜索用户定义对象的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到搜索-用户定义-使用二进制搜索从列表中选择对象-使用比较器/](https://www.geeksforgeeks.org/java-program-to-search-user-defined-object-from-a-list-by-using-binary-search-using-comparator/)

Java 中的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)界面可以用来比较用户定义的对象。比较器接口存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中。[二分搜索法](https://www.geeksforgeeks.org/binary-search/)是一种搜索算法，使用除法和征服规则来搜索列表或数组中元素的存在。二分搜索法算法只适用于排序列表。如果列表没有排序，搜索可能会返回未定义的结果。实现集合接口的预定义类也实现类似的接口。因此，当对预定义包装类的对象执行二分搜索法时，对象以自然顺序排序，然后对排序列表执行二分搜索法。默认情况下，用户定义的类不实现 Java 中的**可比**接口。对于用户定义的类，比较器接口非常有用。比较器接口允许比较用户定义类的特定属性。比较器接口也可以用来比较属于不同类的两个不同的对象。实现比较器接口的类覆盖接口的 **compare()** 方法。以下示例处理创建用户定义的对象，并使用比较器接口对对象进行排序，最后执行二分搜索法运算以获取所需对象的索引。

**语法**

```java
public static int binarySearch(List list, T key)
```

**参数:**

*   **列表:**要执行二分搜索法操作的对象列表。
*   **键:**要查找的对象

**返回值:**返回关键元素的索引。如果找不到键元素，则返回的索引为(-(插入点)–1)。

**例 1:**

创建的学生班级具有学生 id、学生姓名和学生标记等属性。学生类对象列表没有按排序顺序排列。使用传递给 [Collections.sort()](https://www.geeksforgeeks.org/collections-sort-java-examples/) 方法的比较器对象对学生对象列表进行排序。使用[集合，binarySearch()](https://www.geeksforgeeks.org/collections-binarysearch-java-examples/) 方法对已排序的学生列表执行二分搜索法。如果找到目标对象，则返回相应的索引，否则返回的索引为-(插入点)–1。插入点是目标元素必须放在列表中的索引，如果它不存在的话。每个学生的学生证都是唯一的，因此用于对学生列表进行排序。比较()方法在**学生组件**类中被覆盖。如果两个学生具有相同的学生 id，compare()方法返回 0，如果 s1 的学生 id 大于 s2，则返回+1，否则返回-1。学生列表按升序排序。最后，对排序后的对象调用二分搜索法，并将索引所需的对象打印到控制台。

**代码实现**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;

class Student {

    // attributes
    int sid;
    String name;
    int marks;

    // constructor
    public Student(int sid, String name, int marks)
    {
        super();
        this.sid = sid;
        this.name = name;
        this.marks = marks;
    }

    // returns student id
    public int getSid() { return sid; }

    // returns student name
    public String getName() { return name; }

    // returns marks
    public int getMarks() { return marks; }

    public void setSid(int sid) { this.sid = sid; }
    public void setName(String name) { this.name = name; }
    public void setMarks(int marks) { this.marks = marks; }
}

// Comparator to sort a list
class StudentComp implements Comparator<Student> {
    @Override public int compare(Student s1, Student s2)
    {
        if (s1.getSid() == s2.getSid()) {
            return 0;
        }
        else if (s1.getSid() > s2.getSid()) {
            return 1;
        }
        else if (s1.getSid() < s2.getSid()) {
            return -1;
        }
        return -1;
    }
}

public class BinarySearchDemo {

    public static void main(String[] args)
    {

        // list of students
        ArrayList<Student> l = new ArrayList<Student>();

        // Add students
        l.add(new Student(100, "Jack", 95));
        l.add(new Student(101, "Jane", 98));
        l.add(new Student(199, "Mary", 90));
        l.add(new Student(105, "Beck", 75));
        l.add(new Student(104, "Betty", 85));
        l.add(new Student(103, "Archie", 96));
        l.add(new Student(108, "Nate", 89));
        l.add(new Student(109, "Liam", 100));

        // sort the list
        Collections.sort(l, new StudentComp());

        Student searchKey = new Student(109, "Liam", 100);

        // index of the target
        int index1 = Collections.binarySearch(
            l, searchKey, new StudentComp());
        System.out.println("Index of the searched key: "
                           + index1);

        searchKey = new Student(99, "Jennifer", 60);
        int index2 = Collections.binarySearch(
            l, searchKey, new StudentComp());
        System.out.println("Index of the searched key: "
                           + index2);
    }
}
```

**Output**

```java
Index of the searched key: 6
Index of the searched key: -1
```

**例 2:**

在本例中，学生列表按照学生类的标记属性降序排列。因此，前面示例中的相同对象现在有了不同的索引。在新列表上执行二分搜索法操作，因此所需元素的索引被返回并打印到输出中。

**代码实现**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;

class Student {

    // attributes
    int sid;
    String name;
    int marks;

    // constructor
    public Student(int sid, String name, int marks)
    {
        super();
        this.sid = sid;
        this.name = name;
        this.marks = marks;
    }

    // returns student id
    public int getSid() { return sid; }

    // returns name
    public String getName() { return name; }

    // returns marks
    public int getMarks() { return marks; }

    public void setSid(int sid) { this.sid = sid; }
    public void setName(String name) { this.name = name; }
    public void setMarks(int marks) { this.marks = marks; }
}

// comparator to sort
class StudentComp implements Comparator<Student> {
    @Override public int compare(Student s1, Student s2)
    {
        if (s1.getMarks() == s2.getMarks()) {
            return 0;
        }
        else if (s1.getMarks() < s2.getMarks()) {
            return 1;
        }

        return -1;
    }
}

public class BinarySearchDemo {

    public static void main(String[] args)
    {

        // list of students
        ArrayList<Student> l = new ArrayList<Student>();

        // Add students
        l.add(new Student(100, "Jack", 95));
        l.add(new Student(101, "Jane", 98));
        l.add(new Student(199, "Mary", 90));
        l.add(new Student(105, "Beck", 75));
        l.add(new Student(104, "Betty", 85));
        l.add(new Student(103, "Archie", 96));
        l.add(new Student(108, "Nate", 89));
        l.add(new Student(109, "Liam", 100));

        // sort the list
        Collections.sort(l, new StudentComp());

        for (int i = 0; i < l.size(); i++)
            System.out.println(i + " " + l.get(i).getName()
                               + " " + l.get(i).getMarks());

        // search the target
        Student searchKey = new Student(109, "Liam", 100);
        int index1 = Collections.binarySearch(
            l, searchKey, new StudentComp());
        System.out.println("Index of the searched key: "
                           + index1);

        searchKey = new Student(99, "Jennifer", 60);
        int index2 = Collections.binarySearch(
            l, searchKey, new StudentComp());
        System.out.println("Index of the searched key: "
                           + index2);
    }
}
```

**Output**

```java
0 Liam 100
1 Jane 98
2 Archie 96
3 Jack 95
4 Mary 90
5 Nate 89
6 Betty 85
7 Beck 75
Index of the searched key: 0
Index of the searched key: -9
```