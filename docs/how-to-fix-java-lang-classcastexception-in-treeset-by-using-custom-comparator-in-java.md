# 如何在 java 中使用自定义比较器修复 TreeSet 中的 java.lang.ClassCastException？

> 原文:[https://www . geesforgeks . org/how-fix-Java-lang-class castexception-in-treeset-by-custom-comparator-in-Java/](https://www.geeksforgeeks.org/how-to-fix-java-lang-classcastexception-in-treeset-by-using-custom-comparator-in-java/)

此错误由 [**TreeSet**](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 引发，因为 TreeSet 用于按排序顺序存储元素，如果指定的元素无法与集合中的当前元素进行比较，则 TreeSet 将无法按排序顺序存储元素，因此 TreeSet 引发类强制转换异常。

**如何修复这个错误？**

*   通过在 TreeSet 构造函数中提供自定义的比较器。

在像 Integer、Double 等包装类中，比较器接口已经实现，所以我们不需要担心。但是，每当我们在 TreeSet 中使用用户定义的类时，我们都必须用上述方法之一。

**方法:** *通过在 TreeSet 构造函数*中提供自定义比较器

与可比不同，比较器位于我们正在比较的元素类型的外部。这是一个单独的班级。我们创建多个单独的类(实现比较器)来由不同的成员进行比较。

*   创建一个实现 Comparator 的类(从而创建 Comparator()方法，该方法执行 compareTo()以前完成的工作)。
*   创建比较器类的实例。
*   调用重载的 sort()方法，给它实现 Comparator 的类的列表和实例。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to fix java.lang.ClassCastException
// in TreeSet using Comparator

import java.util.Comparator;
import java.util.TreeSet;

class friendsMarks {
    // class field
    String name;
    String nickName;
    int marks;

    // parameterised constructor
    public friendsMarks(String name, String nickName,
                        int marks)
    {
        this.name = name;
        this.nickName = nickName;
        this.marks = marks;
    }

    // getter for name
    public String getName() { return name; }

    // setter for name
    public void setName(String name) { this.name = name; }

    // getter for marks
    public int getMarks() { return marks; }

    // setter for marks
    public void setMarks(int marks) { this.marks = marks; }

    // getter for nickname
    public String getNickName() { return nickName; }

    // setter for nickname
    public void setNickName(String nickName)
    {
        this.nickName = nickName;
    }

    //@Override toString method
    public String toString()
    {
        return "friendsMarks{"
            + "name='" + name + '\'' + ", nickName='"
            + nickName + '\'' + ", marks=" + marks + '}';
    }
}

// for comparing names
class nameCompare implements Comparator<friendsMarks> {

    @Override
    public int compare(friendsMarks friend1,
                       friendsMarks friend2)
    {
        return friend1.getName().compareTo(
            friend2.getName());
    }
}

// for comparing marks
class marksCompare implements Comparator<friendsMarks> {

    @Override
    public int compare(friendsMarks f1, friendsMarks f2)
    {
        if (f1.getMarks() > f2.getMarks()) {
            return 1;
        }
        else {
            return -1;
        }
    }
}

// for comparing nick name
class nickNameCompare implements Comparator<friendsMarks> {

    @Override
    public int compare(friendsMarks obj1, friendsMarks obj2)
    {
        return obj1.getNickName().compareTo(
            obj2.getNickName());
    }
}
public class Main {

    public static void main(String[] args)
    {

        // Creating TreeSet
        // and we have to pass Comparator object
        // of marksCompare class
        // in the TreeSet constructor
        // so that we can sort according to the marks
        TreeSet<friendsMarks> treeSet
            = new TreeSet<>(new marksCompare());

        // adding elements to TreeSet
        treeSet.add(new friendsMarks("Raushan", "Chamgader", 99));
        treeSet.add(new friendsMarks("Yashdeep", "Dopa", 95));
        treeSet.add(new friendsMarks("Rupesh", "Gian", 92));
        treeSet.add(new friendsMarks("Shivam", "Gorilla", 47));
        treeSet.add(new friendsMarks("Sarthak", "Nagin", 78));
        treeSet.add(new friendsMarks("Sonika", "Chipkali", 67));
        treeSet.add(new friendsMarks("Himanshu", "Lalten", 57));

        System.out.println("Sorting on the basis of marks");

        // Displaying using loop
        for (friendsMarks tree : treeSet)
            System.out.println(tree);

        // Creating TreeSet
        // and we have to pass Comparator object
        // of nameCompare class
        // in the TreeSet constructor
        // so that we can sort according to the name
        TreeSet<friendsMarks> treeSet1
            = new TreeSet<>(new nameCompare());

        // adding elements to TreeSet
        treeSet1.add(new friendsMarks("Raushan", "Chamgader", 99));
        treeSet1.add(new friendsMarks("Yashdeep", "Dopa", 95));
        treeSet1.add(new friendsMarks("Rupesh", "Gian", 92));
        treeSet1.add(new friendsMarks("Shivam", "Gorilla", 47));
        treeSet1.add(new friendsMarks("Sarthak", "Nagin", 78));
        treeSet1.add(new friendsMarks("Sonika", "Chipkali", 67));
        treeSet1.add(new friendsMarks("Himanshu", "Lalten", 57));

        // Displaying using loop
        System.out.println("\n\nSorting on the basis of name");

        for (friendsMarks tree : treeSet1)
            System.out.println(tree);

        // Creating TreeSet
        // and we have to pass Comparator object
        // of nickNameCompare class
        // in the TreeSet constructor
        // so that we can sort according to the nickname
        TreeSet<friendsMarks> treeSet2
            = new TreeSet<>(new nickNameCompare());

        // adding elements to TreeSet
        treeSet2.add(new friendsMarks("Raushan", "Chamgader", 99));
        treeSet2.add(new friendsMarks("Yashdeep", "Dopa", 95));
        treeSet2.add(new friendsMarks("Rupesh", "Gian", 92));
        treeSet2.add(new friendsMarks("Shivam", "Gorilla", 47));
        treeSet2.add(new friendsMarks("Sarthak", "Nagin", 78));
        treeSet2.add(new friendsMarks("Sonika", "Chipkali", 67));
        treeSet2.add(new friendsMarks("Himanshu", "Lalten", 57));

        // Displaying using loop
        System.out.println("\n\nSorting on the basis of nick-name");

        for (friendsMarks tree : treeSet2)
            System.out.println(tree);
    }
}
```

**Output**

```
Sorting on the basis of marks
friendsMarks{name='Shivam', nickName='Gorilla', marks=47}
friendsMarks{name='Himanshu', nickName='Lalten', marks=57}
friendsMarks{name='Sonika', nickName='Chipkali', marks=67}
friendsMarks{name='Sarthak', nickName='Nagin', marks=78}
friendsMarks{name='Rupesh', nickName='Gian', marks=92}
friendsMarks{name='Yashdeep', nickName='Dopa', marks=95}
friendsMarks{name='Raushan', nickName='Chamgader', marks=99}

Sorting on the basis of name
friendsMarks{name='Himanshu', nickName='Lalten', marks=57}
friendsMarks{name='Raushan', nickName='Chamgader', marks=99}
friendsMarks{name='Rupesh', nickName='Gian', marks=92}
friendsMarks{name='Sarthak', nickName='Nagin', marks=78}
friendsMarks{name='Shivam', nickName='Gorilla', marks=47}
friendsMarks{name='Sonika', nickName='Chipkali', marks=67}
friendsMarks{name='Yashdeep', nickName='Dopa', marks=95}

Sorting on the basis of nick-name
friendsMarks{name='Raushan', nickName='Chamgader', marks=99}
friendsMarks{name='Sonika', nickName='Chipkali', marks=67}
friendsMarks{name='Yashdeep', nickName='Dopa', marks=95}
friendsMarks{name='Rupesh', nickName='Gian', marks=92}
friendsMarks{name='Shivam', nickName='Gorilla', marks=47}
friendsMarks{name='Himanshu', nickName='Lalten', marks=57}
friendsMarks{name='Sarthak', nickName='Nagin', marks=78}
```