# Java 中的 Collections.sort()，示例

> 原文:[https://www . geesforgeks . org/collections-sort-Java-examples/](https://www.geeksforgeeks.org/collections-sort-java-examples/)

**java.util.Collections . sort()**方法存在于 Java . util . collections 类中。用于对集合中指定的[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)中的元素进行升序排序。
它的工作原理类似于 [java.util.Arrays.sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 方法，但是它更好，因为它可以对 Array 的元素以及链表、队列和其中的更多元素进行排序。

```
public static void sort(List myList)

myList : A List type object we want to sort.

This method doesn't return anything

```

示例:

```

Let us suppose that our list contains
{"Geeks For Geeks", "Friends", "Dear", "Is", "Superb"}

After using Collection.sort(), we obtain a sorted list as
{"Dear", "Friends", "Geeks For Geeks", "Is", "Superb"}

```

**按升序对数组列表进行排序**

```
// Java program to demonstrate working of Collections.sort()
import java.util.*;

public class Collectionsorting
{
    public static void main(String[] args)
    {
        // Create a list of strings
        ArrayList<String> al = new ArrayList<String>();
        al.add("Geeks For Geeks");
        al.add("Friends");
        al.add("Dear");
        al.add("Is");
        al.add("Superb");

        /* Collections.sort method is sorting the
        elements of ArrayList in ascending order. */
        Collections.sort(al);

        // Let us print the sorted list
        System.out.println("List after the use of" +
                           " Collection.sort() :\n" + al);
    }
}
```

输出:

```
List after the use of Collection.sort() :
[Dear, Friends, Geeks For Geeks, Is, Superb]

```

**按降序排列数组列表**

```
// Java program to demonstrate working of Collections.sort()
// to descending order.
import java.util.*;

public class Collectionsorting
{
    public static void main(String[] args)
    {
        // Create a list of strings
        ArrayList<String> al = new ArrayList<String>();
        al.add("Geeks For Geeks");
        al.add("Friends");
        al.add("Dear");
        al.add("Is");
        al.add("Superb");

        /* Collections.sort method is sorting the
        elements of ArrayList in ascending order. */
        Collections.sort(al, Collections.reverseOrder());

        // Let us print the sorted list
        System.out.println("List after the use of" +
                           " Collection.sort() :\n" + al);
    }
}
```

输出:

```
List after the use of Collection.sort() :
[Superb, Is, Geeks For Geeks, Friends, Dear]

```

**根据用户定义的条件对数组列表进行排序。**
我们可以使用[比较器接口](https://www.geeksforgeeks.org/comparator-interface-java/)来达到这个目的。

```
// Java program to demonstrate working of Comparator
// interface and Collections.sort() to sort according
// to user defined criteria.
import java.util.*;
import java.lang.*;
import java.io.*;

// A class to represent a student.
class Student
{
    int rollno;
    String name, address;

    // Constructor
    public Student(int rollno, String name,
                               String address)
    {
        this.rollno = rollno;
        this.name = name;
        this.address = address;
    }

    // Used to print student details in main()
    public String toString()
    {
        return this.rollno + " " + this.name +
                           " " + this.address;
    }
}

class Sortbyroll implements Comparator<Student>
{
    // Used for sorting in ascending order of
    // roll number
    public int compare(Student a, Student b)
    {
        return a.rollno - b.rollno;
    }
}

// Driver class
class Main
{
    public static void main (String[] args)
    {
        ArrayList<Student> ar = new ArrayList<Student>();
        ar.add(new Student(111, "bbbb", "london"));
        ar.add(new Student(131, "aaaa", "nyc"));
        ar.add(new Student(121, "cccc", "jaipur"));

        System.out.println("Unsorted");
        for (int i=0; i<ar.size(); i++)
            System.out.println(ar.get(i));

        Collections.sort(ar, new Sortbyroll());

        System.out.println("\nSorted by rollno");
        for (int i=0; i<ar.size(); i++)
            System.out.println(ar.get(i));
    }
}
```

输出:

```
Unsorted
111 bbbb london
131 aaaa nyc
121 cccc jaipur

Sorted by rollno
111 bbbb london
121 cccc jaipur
131 aaaa nyc

```

**[arrays . sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)vs collections . sort()**
arrays . sort 适用于也可以是原始数据类型的数组。[收藏](https://www.geeksforgeeks.org/collections-in-java-2/)。sort()适用于对象集合，如[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)、[链接列表](http://geeksquiz.com/linked-list-in-java/)等。

在创建给定数组项的数组列表后，我们可以使用 Collections.sort()对数组进行排序。

```
// Using Collections.sort() to sort an array
import java.util.*;
public class Collectionsort
{
    public static void main(String[] args)
    {
        // create an array of string objs
        String domains[] = {"Practice", "Geeks",
                             "Code", "Quiz"};

        // Here we are making a list named as Collist
        List colList =
            new ArrayList(Arrays.asList(domains));

        // Collection.sort() method is used here
        // to sort the list elements.
        Collections.sort(colList);

        // Let us print the sorted list
        System.out.println("List after the use of" +
                           " Collection.sort()  :\n" +
                           colList);
    }
}
```

输出:

```
List after the use of Collection.sort()  :
[Code, Geeks, Practice, Quiz]

```

本文由**莫希特·古普塔**供稿。文章希望对尊敬的极客有用。
如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
。