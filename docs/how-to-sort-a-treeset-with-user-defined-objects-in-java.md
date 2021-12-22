# 如何用 Java 对用户定义对象的树集进行排序？

> 原文:[https://www . geesforgeks . org/如何使用 java 中的用户定义对象对树集进行排序/](https://www.geeksforgeeks.org/how-to-sort-a-treeset-with-user-defined-objects-in-java/)

[**【比较器】**](https://www.geeksforgeeks.org/comparator-interface-java/) 界面对自定义类的对象进行排序。**比较器**类的一个对象能够比较两个不同类的两个对象。以下功能比较 **obj1** 和 **obj2**

*   **树集**实现**排序集**界面。因此，不允许重复值。
*   树集中的对象以排序和升序存储。
*   **TreeSet** 不保留元素的插入顺序，但元素按键排序。
*   如果我们依赖于默认的自然排序顺序，那么插入到树中的对象应该是同类的和可比较的。**树集**不允许插入异类对象。它会抛出一个**级异常**

由于**树集**实现了**排序集**界面，因此元素默认按升序排序。但是如果我们想在排序中进行改变，比如按照递减的顺序进行排序，或者按照姓名、分数、工资(这些都是用户定义的类)进行排序，比如任何方式。

所以解决这一切的办法就是我们可以通过显式实现**比较器**类**来进行排序。**

**语法:**

```java
public int compare(Object obj1, Object obj2):
```

**进场:**

*   **比较器**界面用于对自定义类的对象进行排序。
*   该接口存在于 **java.util 包**中，包含 2 个方法**比较**(对象 obj1，对象 obj2)和**等于**(对象元素)。
*   使用比较器，我们可以根据数据成员对元素进行排序。例如，它可能在标记、名称或其他任何东西上。

用于对列表元素进行排序的 Collections 类的方法用于根据给定的比较器对列表元素进行排序。

```java
// To sort a given list. ComparatorClass must implement 
// Comparator interface.

public void sort(List list, ComparatorClass c)
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Sort a TreeSet with
// User Defined Objects

import java.io.*;
import java.util.*;
class students{

    private int marks;
    private String name;

    // constructor
    public students(int value, String name)
    {
        this.marks=value;
        this.name=name;
    }
    public String getName()
    {
        return name;
    }
    public void setName(String name)
    {
        this.name= name;
    }

    public int getMarks()
    {
        return marks;
    }

}

// Comparator class will override the compare
// method which will compare the tw objects
// passed in the parameter
class myMarksComparator implements Comparator<students>
{

    public int compare(students s1, students s2)
    {
        return s1.getMarks()-s2.getMarks();
    }
}

class myNameComparator implements Comparator<students>
{
    public int compare(students s1, students s2)
    {
        return s1.getName().compareTo(s2.getName());
    }
}

class GFG {

    public static void main (String[] args){

        // Creating the TreeSet with Comparator object passed
        // as the parameter which will sort the user defined
        // objects of TreeSet
        TreeSet<students> set = new TreeSet<students>(new myMarksComparator());

        set.add(new students(450,"Sam"));
        set.add(new students(341,"Ronaldo"));
        set.add(new students(134,"Daniel"));
        set.add(new students(590,"George"));

        System.out.println("increasing Order with the Marks");

        // Printing the TreeSet elements
        for(students ele: set)
        {
            System.out.print(ele.getName()+" "+ele.getMarks());
            System.out.println();
        }

        TreeSet<students> mrks= new TreeSet<students>(new myNameComparator());

        mrks.add(new students(450,"Sam"));
        mrks.add(new students(341,"Ronaldo"));
        mrks.add(new students(134,"Daniel"));
        mrks.add(new students(590,"George"));

        System.out.println();

        for(students ele : mrks)
        {
            System.out.print(ele.getName() +" "+ ele.getMarks());
            System.out.println();
        }

    }
}
```

**Output**

```java
-------increasing Order with the Marks
Daniel 134
Ronaldo 341
Sam 450
George 590

Daniel 134
George 590
Ronaldo 341
Sam 450
```