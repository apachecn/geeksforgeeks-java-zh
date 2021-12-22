# 如何在 Java 中使用可比接口对 LinkedHashSet 元素进行排序？

> 原文:[https://www . geesforgeks . org/how-sort-link edhashset-elements-使用 java 中的可比接口/](https://www.geeksforgeeks.org/how-to-sort-linkedhashset-elements-using-comparable-interface-in-java/)

链接哈希集是[哈希集](https://www.geeksforgeeks.org/hashset-in-java/)的有序版本，它维护所有元素的双向链表。当需要维护迭代顺序时，使用这个类。当遍历 HashSet 时，顺序是不可预测的，而 LinkedHashSet 让我们按照元素插入的顺序遍历元素。

为了首先在 java 中使用[compatible](https://www.geeksforgeeks.org/comparable-vs-comparator-in-java/)接口对 LinkedHashSet 元素进行排序，我们创建了一个实现 compatible 接口的类 Student。在这个类中，我们覆盖了 [compareTo()](https://www.geeksforgeeks.org/java-equals-compareto-equalsignorecase-and-compare/) 方法。

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

然后我们将集合传递给 TreeSet 构造函数来对元素进行排序。

```
// TreeSet to sort LinkedHashSet using comparable
TreeSet<Student> tree_set = new TreeSet<>(set);
```

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate how to Sort LinkedHashSet using
// Comparable interface
import java.util.*;

// Student class implements comparable interface
class Student implements Comparable<Student> {
    Integer marks;

    Student(Integer marks) { this.marks = marks; }

    // override toString method
    public String toString() { return (" " + this.marks); }

    // Override compareTo method to sort LinkedHashSet in
    // ascending order
    public int compareTo(Student stu)
    {
        return this.marks.compareTo(stu.marks);
    }
}

class GFG {
    public static void main(String[] args)
    {

        // New LinkedHashSet
        LinkedHashSet<Student> set = new LinkedHashSet<>();

        // Adding elements to the set
        set.add(new Student(500));
        set.add(new Student(300));
        set.add(new Student(400));
        set.add(new Student(100));
        set.add(new Student(200));

        // Print Before sort
        System.out.println(
            "Before sort elements in ascending order : "
            + set);

        // TreeSet to sort LinkedHashSet using comparable
        TreeSet<Student> tree_set = new TreeSet<>(set);

        // Print after sorting
        System.out.println(
            "After sort elements in ascending order : "
            + tree_set);
    }
}
```

**Output**

```
Before sort elements in ascending order : [ 500,  300,  400,  100,  200]
After sort elements in ascending order : [ 100,  200,  300,  400,  500]
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program demonstrate how to Sort LinkedHashSet using
// Comparable interface
import java.util.*;

// Student class implements comparable interface
class Student implements Comparable<Student> {
    Integer marks;

    Student(Integer marks) { this.marks = marks; }

    // override toString method
    public String toString() { return (" " + this.marks); }

    // Override compareTo method to sort LinkedHashSet in
    // descending order
    public int compareTo(Student stu)
    {
        return stu.marks.compareTo(this.marks);
    }
}

class GFG {
    public static void main(String[] args)
    {

        // New LinkedHashSet
        LinkedHashSet<Student> set = new LinkedHashSet<>();

        // Adding elements to the set
        set.add(new Student(500));
        set.add(new Student(300));
        set.add(new Student(400));
        set.add(new Student(100));
        set.add(new Student(200));

        // Print Before sort
        System.out.println(
            "Before sort elements in descending order : "
            + set);

        // TreeSet to sort LinkedHashSet using comparable
        TreeSet<Student> tree_set = new TreeSet<>(set);

        // Print after sorting
        System.out.println(
            "After sort elements in descending order : "
            + tree_set);
    }
}
```

**输出:**

```
Before sort elements in descending order : [ 500,  300,  400,  100,  200]
After sort elements in descending order : [ 500,  400,  300,  200,  100]

```