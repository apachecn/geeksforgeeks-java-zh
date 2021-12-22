# 如何用 Java 打印收藏？

> 原文:[https://www . geesforgeks . org/how-print-a-collection-in-Java/](https://www.geeksforgeeks.org/how-to-print-a-collection-in-java/)

集合是一组保存对程序中其他对象的引用的对象。在做同样的事情时，我们已经研究了一个数据结构- [**HashMap**](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) ，它在内部以同样的方式工作。所以我们想出了一个用 java 打印 Collection 的方法，那就是通过 HashMap。现在更进一步，我们遇到了-收集-框架。

**toString 方法**被 Java 中的所有类继承，以便通过重写 toString 方法来打印 Java 中的任何集合。重写后，我们可以使用 for-each 循环遍历集合，以打印集合中的所有对象

java 中的集合可以通过以下两种方式打印:

*   打印用户定义的数组列表
*   打印用户定义的哈希表

### 方法 1:打印用户定义的[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to print an arraylist of an
// user-defined collection
import java.util.*;

class GFG {
    String name;
    int rollNo;

    // constructor of class GFG
    GFG(String s, int n)
    {
        name = s;
        rollNo = n;
    }

    // over-riding the toString method
    // to print the collection
    public String toString()
    {
        return "Name : " + name + " | Roll No : " + rollNo;
    }

    // Driver Main Method
    public static void main(String[] args)
    {
        // creating an arraylist of user-defined collection
        ArrayList<GFG> arr = new ArrayList<GFG>();

        // creating objects of class GFG
        GFG t1 = new GFG("John", 101);
        GFG t2 = new GFG("Paul", 102);
        GFG t3 = new GFG("Jack", 103);
        GFG t4 = new GFG("Jose", 104);

        // adding objects to arraylist
        arr.add(t1);
        arr.add(t2);
        arr.add(t3);
        arr.add(t4);

        // printing the collection
        for (GFG c : arr)
            System.out.println(c);
    }
}
```

**Output**

```java
Name : John | Roll No : 101
Name : Paul | Roll No : 102
Name : Jack | Roll No : 103
Name : Jose | Roll No : 10

```

### 方法 2:打印用户定义的[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program printing ArrayList
// of an user-defined collection

// Importing Classes/Files
import java.util.*;

public class GFG {
    String firstName;
    String lastName;

    // Constructor
    GFG(String fn, String ln)
    {
        firstName = fn;
        lastName = ln;
    }

    // Function- toString()
    public String toString()
    {
        // Over-riding the toString method to print the
        // collection
        return "| First Name : " + firstName
            + " | LastName : " + lastName;
    }

    // Driver Main Method
    public static void main(String[] args)
    {
        // Creating a hashmap with key as ID  and
        // value as user defined class
        HashMap<Integer, GFG> hm
            = new HashMap<Integer, GFG>();

        // creating objects
        GFG p1
            = new GFG("Mohit", "Singh");
        GFG p2
            = new GFG("Tarun", "Anand");
        GFG p3
            = new GFG("Madhu", "Singh");
        GFG p4
            = new GFG("Rohit", "Ahuja");

        // adding mappings
        hm.put(101, p1);
        hm.put(102, p2);
        hm.put(103, p3);
        hm.put(104, p4);

        // printing the collection
        for (Map.Entry m : hm.entrySet())
            System.out.println(m.getKey() + " "
                               + m.getValue().toString());
    }
}
```

**Output**

```java
101 | First Name : Mohit | LastName : Singh
102 | First Name : Tarun | LastName : Anand
103 | First Name : Madhu | LastName : Singh
104 | First Name : Rohit | LastName : Ahuja
```