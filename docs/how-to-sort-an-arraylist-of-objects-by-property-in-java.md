# 如何在 Java 中按属性对对象的数组列表进行排序？

> 原文:[https://www . geesforgeks . org/如何按 java 中的属性对对象数组列表进行排序/](https://www.geeksforgeeks.org/how-to-sort-an-arraylist-of-objects-by-property-in-java/)

Java 中的 [**数组列表**](https://www.geeksforgeeks.org/custom-arraylist-java/) (相当于 C++中的向量)具有动态大小。它可以根据大小缩小或扩展。ArrayList 是集合框架的一部分，存在于 java.util 包中。

```
ArrayList <E> list = new ArrayList <> ();
```

**方法 1:**

1.  在下面的程序中，我们定义了一个带有字符串属性 *customProperty* 的 CustomObject 类。
2.  我们还添加了一个初始化属性的构造函数和一个 getter 函数 *getCustomProperty()* ，返回 *customProperty* 。
3.  在 *main()* 方法中，我们创建了一个自定义对象列表的数组*列表*，用 5 个对象初始化。
4.  对于给定属性的*列表*的排序，我们使用*列表*的*排序()*方法。
5.  **排序()方法**取待排序的列表(最终排序列表也相同)和一个***比较器*** **。**

在我们的例子中， [**比较器**](https://www.geeksforgeeks.org/comparator-interface-java/) 是一个λ——

*   从列表 *o1* 和 o2 中选取两个对象，
*   比较两个对象的 *customProperty* 使用 ***compareTo()*** 方法，
*   最后，如果 o1 的属性大于 o2，则返回正数，如果 o1 的属性小于 o2，则返回负数，如果它们相等，则返回零。
*   基于此，列表根据从最小到最大的属性进行排序，并存储回列表。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to sort the ArrayList
// of objects by property

import java.util.*;

// Define a custom class with custom property
// It takes and stores custom objects
class CustomObject {

    private String customProperty;

    public CustomObject(String property)
    {
        this.customProperty = property;
    }

    public String getCustomProperty()
    {
        return this.customProperty;
    }
}

public class GFG {

    // printing sorted ArrayList objects using enchanced
    // for loop
    public static void print(ArrayList<CustomObject> list)
    {
        for (CustomObject obj : list) {
            System.out.println(obj.getCustomProperty());
        }
    }

    // Comparison done using compareTo function
    public static void sort(ArrayList<CustomObject> list)
    {

        list.sort((o1, o2)
                      -> o1.getCustomProperty().compareTo(
                          o2.getCustomProperty()));
    }

    // Adding custom objects
    public static void add(ArrayList<CustomObject> list)
    {
        list.add(new CustomObject("Z"));
        list.add(new CustomObject("A"));
        list.add(new CustomObject("B"));
        list.add(new CustomObject("X"));
        list.add(new CustomObject("Aa"));
    }

    public static void main(String[] args)
    {
        // Declare ArrayList with custom class

        ArrayList<CustomObject> list = new ArrayList<>();
        add(list);
        sort(list);
        print(list);
    }
}
```

**Output**

```
A
Aa
B
X
Z
```

**方法 2:使用可比和比较器**

当数组列表是自定义对象类型时，在这种情况下，我们使用两种排序方法:比较器或可比较的，在这种情况下，不能直接使用 Collections.sort()，因为它会产生错误，因为它只对特定的数据类型进行排序，而不对用户定义的类型进行排序。

**用可比排序数组列表:**

1.  这里的自定义对象类型类“学生”将实现可比较类<student>。</student>
2.  这将覆盖 Comparable 类的 compareTo()方法，该方法将 class Student 的对象作为参数，我们需要比较值/属性，通过这些值/属性我们希望对列表进行排序，并在 compareTo()函数中相应地返回。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to sort ArrayList of
// custom object using Comparable class

import java.util.*;
class ArrayListSorting {

    public static void main(String args[])
    {
        ArrayList<Student> arraylist
            = new ArrayList<Student>();
        arraylist.add(new Student(12, "Riya", 15));
        arraylist.add(new Student(14, "Mahima", 16));
        arraylist.add(new Student(13, "Shubhi", 15));

        Collections.sort(arraylist);

        for (Student str : arraylist) {
            System.out.println(str);
        }
    }
}

public class Student implements Comparable<Student> {
    private String studentname;
    private int rollno;
    private int studentage;

    public Student(int rollno, String studentname,
                   int studentage)
    {
        this.rollno = rollno;
        this.studentname = studentname;
        this.studentage = studentage;
    }

    // getter and setter functions

    public String getStudentname() { return studentname; }

    public void setStudentname(String studentname)
    {
        this.studentname = studentname;
    }

    public int getRollno() { return rollno; }

    public void setRollno(int rollno)
    {
        this.rollno = rollno;
    }

    public int getStudentage() { return studentage; }

    public void setStudentage(int studentage)
    {
        this.studentage = studentage;
    }

    // overriding the compareTo method of Comparable class
    @Override public int compareTo(Student comparestu)
    {
        int compareage
            = ((Student)comparestu).getStudentage();

        //  For Ascending order
        return this.studentage - compareage;

        // For Descending order do like this
        // return compareage-this.studentage;
    }

    @Override public String toString()
    {
        return "[ rollno=" + rollno + ", name="
            + studentname + ", age=" + studentage + "]";
    }
}
```

**Output**

```
[ rollno=12, name=Riya, age=15]
[ rollno=13, name=Shubhi, age=15]
[ rollno=14, name=Mahima, age=16]
```

**用比较器排序数组列表:**

1.  我们将定义另一个类来实现自定义对象类型的比较器类。例如，在下面的代码中，我们的自定义类是 Student，所以我们定义的另一个类将实现 comparattot<student>。</student>
2.  这个类将覆盖 Comparator 类的 compare 方法，该方法接受 Student 类的两个对象作为参数，并根据我们的要求返回比较值，即我们是要按升序还是降序对数组进行排序，以及我们要根据哪个属性对列表进行排序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to sort the ArrayList
// of custom object using Comparator class

import java.util.*;
import java.util.Comparator;
public class Student {
    private String studentname;
    private int rollno;
    private int studentage;

    public Student(int rollno, String studentname,
                   int studentage)
    {
        this.rollno = rollno;
        this.studentname = studentname;
        this.studentage = studentage;
    }

    // getter and setter functions

    public String getStudentname() { return studentname; }

    public void setStudentname(String studentname)
    {
        this.studentname = studentname;
    }

    public int getRollno() { return rollno; }

    public void setRollno(int rollno)
    {
        this.rollno = rollno;
    }

    public int getStudentage() { return studentage; }

    public void setStudentage(int studentage)
    {
        this.studentage = studentage;
    }

    public static Comparator<Student> StuNameComparator = new Comparator<Student>() {

      public int compare(Student s1, Student s2)
              {

                  String StudentName1
                      = s1.getStudentname().toUpperCase();
                  String StudentName2
                      = s2.getStudentname().toUpperCase();

                  // ascending order
                  return StudentName1.compareTo(
                      StudentName2);

                  // descending order
                  // return
                  // StudentName2.compareTo(StudentName1);
              }
          };

    // Comparator for sorting the list by roll no
    public static Comparator<Student> StuRollno = new Comparator<Student>() {
              public int compare(Student s1, Student s2)
              {

                  int rollno1 = s1.getRollno();
                  int rollno2 = s2.getRollno();

                  // For ascending order
                  return rollno1 - rollno2;

                  // For descending order
                  // rollno2-rollno1;
              }
          };

    @Override public String toString()
    {
        return "[ rollno=" + rollno + ", name="
            + studentname + ", age=" + studentage + "]";
    }
}

class Details {

    public static void main(String args[])
    {
        ArrayList<Student> arraylist
            = new ArrayList<Student>();

        arraylist.add(new Student(101, "Zues", 26));
        arraylist.add(new Student(505, "Abey", 24));
        arraylist.add(new Student(809, "Vignesh", 32));

        // Sorting based on Student Name
        System.out.println("Student Name Sorting:");

        Collections.sort(arraylist,
                         Student.StuNameComparator);

        for (Student str : arraylist) {
            System.out.println(str);
        }

        // Sorting on Rollno property
        System.out.println("RollNum Sorting:");

        Collections.sort(arraylist, Student.StuRollno);

        for (Student str : arraylist) {
            System.out.println(str);
        }
    }
}
```

**Output**

```
Student Name Sorting:
[ rollno=505, name=Abey, age=24]
[ rollno=809, name=Vignesh, age=32]
[ rollno=101, name=Zues, age=26]
RollNum Sorting:
[ rollno=101, name=Zues, age=26]
[ rollno=505, name=Abey, age=24]
[ rollno=809, name=Vignesh, age=32]
```