# 如何在 Java 中从 LinkedHashSet 中找到用户定义的对象？

> 原文:[https://www . geesforgeks . org/how-to-find-user-defined-objects-from-link edhashset-in-Java/](https://www.geeksforgeeks.org/how-to-find-user-defined-objects-from-linkedhashset-in-java/)

[LinkedHashSet](https://www.geeksforgeeks.org/linkedhashset-in-java-with-examples/) 用于存储元素的插入顺序。当需要维护迭代顺序时，使用这个类。当迭代一个 [HashSet](https://www.geeksforgeeks.org/hashset-in-java/) 时，顺序是不可预测的，而 LinkedHashSet 让我们按照元素插入的顺序迭代元素。当使用迭代器循环遍历 LinkedHashSet 时，元素将返回到它们被插入的顺序。

我们有一个类 Student 和一个类型为 Student 的 LinkedHashSet，我们希望看到 LinkedHashSet 是否包含该对象。

```
// Student class
class Student {

  int rollNo;
  String name;

  Student(int r, String s) {
    rollNo = r;
    name = s;
  }
}

// LinkedHashSet of type Student
LinkedHashSet<Student> set = new LinkedHashSet<>();
```

**在 LinkedHashSet 中查找对象有两种方式:**

*   使用 contains()方法
*   在链接数据集上使用迭代

**法 1:使用** [**包含()**](https://www.geeksforgeeks.org/hashset-contains-method-in-java/) 法**法**

我们可以使用 Java 中的 contains()方法在 LinkedHashSet 中找到该对象。Java 中的 contains()方法返回 true，如果对象存在于 LinkedHashSet 中，则返回 false。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find user defined objects from
// LinkedHashSet

import java.util.*;

// Student class
class Student {

    int rollNo;
    String name;

    Student(int r, String s)
    {
        rollNo = r;
        name = s;
    }
}

public class GFG {
    public static void main(String[] args)
    {
        // Objects of Student
        Student stu1 = new Student(1, "Akshay");
        Student stu2 = new Student(2, "Bina");
        Student stu3 = new Student(3, "Chintu");
        Student stu4 = new Student(4, "Dheeraj");

        // New empty LinkedHashSet of type Student
        LinkedHashSet<Student> set = new LinkedHashSet<>();

        // Add objects to set
        set.add(stu1);
        set.add(stu2);
        set.add(stu3);

        // Return true if set contains the obj otherwise,
        // false
        if (set.contains(stu4))
        {
            System.out.println(stu4.name+ " is present in set.");
        }
        else
        {
            System.out.println(stu4.name+ " is not present in set.");
        }
    }
}
```

**Output**

```
Dheeraj is not present in set.
```

**方法二:使用** [**迭代**](https://www.geeksforgeeks.org/java-program-to-iterate-linkedhashset-elements/) **到 LinkedHashSet:**

我们还可以在 LinkedHashSet 中使用迭代来找到该对象。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to find user defined objects from
// LinkedHashSet 

import java.util.*;

// Student class
class Student {

    int rollNo;
    String name;

    Student(int r, String s)
    {
        rollNo = r;
        name = s;
    }
}

public class GFG {
    public static void main(String[] args)
    {
        // Objects of Student
        Student stu1 = new Student(1, "Akshay");
        Student stu2 = new Student(2, "Bina");
        Student stu3 = new Student(3, "Chintu");
        Student stu4 = new Student(4, "Dheeraj");

        // New empty LinkedHashSet of type Student
        LinkedHashSet<Student> set = new LinkedHashSet<>();

        // Add objects to set
        set.add(stu1);
        set.add(stu2);
        set.add(stu3);

        // Using iterate LinkedHashSet
        for (Student stu : set) 
        {
            if (stu == stu2)
            {
                System.out.println(stu.name+ " present in set.");
            }
        }
    }
}
```

**Output**

```
Bina present in set.
```