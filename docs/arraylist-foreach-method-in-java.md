# Java 中的 ArrayList forEach()方法

> 原文:[https://www . geesforgeks . org/ArrayList-foreach-method-in-Java/](https://www.geeksforgeeks.org/arraylist-foreach-method-in-java/)

[**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 的 **forEach()** 方法用于对数组列表中的每个元素执行一定的操作。此方法遍历数组列表的 Iterable 的每个元素，直到该方法处理完所有元素或引发异常。如果方法指定了迭代顺序，则按照迭代顺序执行操作。操作引发的异常被传递给调用方。

除非重写类指定了并发修改策略，否则该操作无法修改元素的基础源，因此我们可以说该方法的行为是未指定的。

[在 Java 中从集合中检索元素](https://www.geeksforgeeks.org/retrieving-elements-from-collection-for-each-iterator-listiterator-enumerationiterator/)。

**语法:**

```java
public void forEach(Consumer<? super E> action)
```

**参数:**该方法取一个参数*动作*，代表每个元素要执行的动作。

**返回:**这个方法不返回任何东西。

**异常:**如果指定的操作为空，此方法将引发 NullPointerException。

下面的程序说明了数组列表的 forEach()方法:

**程序 1:** 在包含数字列表的数组列表上演示 forEach()方法的程序。

```java
// Java Program Demonstrate forEach()
// method of ArrayList

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // create an ArrayList which going to
        // contains a list of Numbers
        ArrayList<Integer> Numbers = new ArrayList<Integer>();

        // Add Number to list
        Numbers.add(23);
        Numbers.add(32);
        Numbers.add(45);
        Numbers.add(63);

        // forEach method of ArrayList and
        // print numbers
        Numbers.forEach((n) -> System.out.println(n));
    }
}
```

**输出:**

```java
23
32
45
63

```

**程序 2:** 在包含学生姓名列表的数组列表上演示 forEach()方法的程序。

```java
// Java Program Demonstrate forEach()
// method of ArrayList

import java.util.*;
public class GFG {

    public static void main(String[] args)
    {
        // create an ArrayList which going to
        // contains a list of Student names which is actually
        // string values
        ArrayList<String> students = new ArrayList<String>();

        // Add Strings to list
        // each string represents student name
        students.add("Ram");
        students.add("Mohan");
        students.add("Sohan");
        students.add("Rabi");

        // print result
        System.out.println("list of Students:");

        // forEach method of ArrayList and
        // print student names
        students.forEach((n) -> print(n));
    }

    // printing student name
    public static void print(String n)
    {
        System.out.println("Student Name is " + n);
    }
}
```

**输出:**

```java
list of Students:
Student Name is Ram
Student Name is Mohan
Student Name is Sohan
Student Name is Rabi

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/ArrayList . html # forEach(Java . util . function . consumer)](https://docs.oracle.com/javase/10/docs/api/java/util/ArrayList.html#forEach(java.util.function.Consumer))