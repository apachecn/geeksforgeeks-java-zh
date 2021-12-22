# 使用带有用户定义对象的比较器对树形图中的关键字进行排序的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-通过使用带有用户定义对象的比较器对树图中的键进行排序的程序/](https://www.geeksforgeeks.org/java-program-to-sort-keys-in-treemap-by-using-comparator-with-user-defined-objects/)

Java 中的[树形图](https://www.geeksforgeeks.org/treemap-in-java/)与[抽象图](https://www.geeksforgeeks.org/abstractmap-in-java/)类一起用于实现[地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/)和[导航地图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)。地图根据其键的自然顺序进行排序，或者通过地图创建时提供的[【比较器】](https://www.geeksforgeeks.org/comparator-interface-java/) 进行排序，具体取决于使用的构造函数。为了通过在 Java 中使用带有用户定义对象的比较器来对 TreeMap 中的键进行排序，我们必须创建一个实现比较器接口的类来覆盖比较方法。

```
// AccordingMarks class that implements the 
// comparator interface to override compare method

class AccordingMarks implements Comparator<Student> {
    public int compare(Student s1, Student s2) {
        return s1.getMarks().compareTo(s2.getMarks());
    }
}
```

在下面的代码中，我们将一个自定义对象作为键传递给 TreeMap，即学生用户定义的类。在这种情况下，我们需要在构造器中传递比较器 **AccordingMarks** ，同时创建根据学生的标记对树形图进行排序的树形图对象。

**示例 1:** 按标记的升序排列键

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate how to sort TreeMap of custom
// class objects
import java.util.*;

// Custom class
class Student {

    private String name;
    private int marks;

    public Student(String name, Integer marks)
    {
        this.name = name;
        this.marks = marks;
    }

    public String getName() { return this.name; }

    public Integer getMarks() { return this.marks; }
    // override toString method
    public String toString()
    {
        return this.name + ": " + marks;
    }
}

// Comparator that sort elements according to marks in
// Ascending order
class AccordingMarks implements Comparator<Student> {
    public int compare(Student s1, Student s2)
    {
        return s1.getMarks().compareTo(s2.getMarks());
    }
}

// Driver Code
public class GFG {
    public static void main(String[] args)
    {

        // New TreeMap of custom class Student
        TreeMap<Student, Integer> map
            = new TreeMap<>(new AccordingMarks());

        // Add elements to TreeMap
        map.put(new Student("Akshay", 400), 1);
        map.put(new Student("Bina", 500), 2);
        map.put(new Student("Chintu", 300), 3);

        System.out.println(
            "TreeMap keys sorting in ascending order of the marks:");

        // Print map using Entry
        for (Map.Entry<Student, Integer> entry :
             map.entrySet()) {
            System.out.println("Key : (" + entry.getKey()
                               + "), Value : "
                               + entry.getValue());
        }
    }
}
```

**输出:**

```
TreeMap keys sorting in ascending order of the marks:
Key : (Chintu: 300), Value : 3
Key : (Akshay: 400), Value : 1
Key : (Bina: 500), Value : 2
```

**示例 2:** 将键按标记的降序排序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate how to sort TreeMap of custom
// class objects
import java.util.*;

// Custom class
class Student {

    private String name;
    private int marks;

    public Student(String name, Integer marks)
    {
        this.name = name;
        this.marks = marks;
    }

    public String getName() { return this.name; }

    public Integer getMarks() { return this.marks; }
    // override toString method
    public String toString()
    {
        return this.name + ": " + marks;
    }
}

// Comparator that sort elements according to marks in
// Descending order
class AccordingMarks implements Comparator<Student> {
    public int compare(Student s1, Student s2)
    {
        return s2.getMarks().compareTo(s1.getMarks());
    }
}

// Driver Code
public class GFG {
    public static void main(String[] args)
    {

        // New TreeMap of custom class Student
        TreeMap<Student, Integer> map
            = new TreeMap<>(new AccordingMarks());

        // Add elements to TreeMap
        map.put(new Student("Akshay", 400), 1);
        map.put(new Student("Bina", 500), 2);
        map.put(new Student("Chintu", 300), 3);

        System.out.println(
            "TreeMap Keys sorted in descending order of the marks: ");

        // Print map using Entry
        for (Map.Entry<Student, Integer> entry :
             map.entrySet()) {
            System.out.println("Key : (" + entry.getKey()
                               + "), Value : "
                               + entry.getValue());
        }
    }
}
```

**输出:**

```
TreeMap Keys sorted in descending order of the marks: 
Key : (Bina: 500), Value : 2
Key : (Akshay: 400), Value : 1
Key : (Chintu: 300), Value : 3
```