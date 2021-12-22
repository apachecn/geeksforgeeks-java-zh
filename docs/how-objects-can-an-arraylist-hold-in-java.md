# 在 Java 中，数组列表如何保存对象？

> 原文:[https://www . geesforgeks . org/how-objects-can-an-ArrayList-hold-in-Java/](https://www.geeksforgeeks.org/how-objects-can-an-arraylist-hold-in-java/)

[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)是集合框架的一部分，存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中。它为我们提供了 Java 中的动态数组，就像 C++中的 Vector 一样。尽管它可能比标准数组慢，但在需要对数组进行大量操作的程序中会很有帮助。

为了理解问题分为两半:

1.  **前半部分:**表示数组列表中普通元素的一般加法。要存储在数组列表中的元素的数据类型是字符串或整数类型。
2.  **后半部分:**制作相同的数组列表，以类对象为元素。

**语法:**声明列表

```java
ArrayList<String> names = new ArrayList<String>();
```

> 这里<string>代表要存储在数组列表中的元素的数据类型。请记住，这不能是任何原始数据类型，如 int 或 float。</string>

**说明:**考虑的子类随机命名为“人”。

**方法:Java 中 List 接口的** [*List.get()* 方法](https://www.geeksforgeeks.org/list-get-method-in-java-with-examples/) 用于获取该列表中给定特定索引处存在的元素。

*   制作一个辅助 java 类。
*   给它一些属性。例如，类别人员可以包括姓名、年龄、号码等
*   创建一个新对象。
*   将上面创建的对象存储在数组列表中。
*   使用 *List.get()* 方法打印上述对象的元素。

**实施:**

*   制作人员类对象。
*   制作一个以人物对象为元素的数组列表。

**(A)前半部分:**表示数组列表中普通元素的一般加法。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to add elements to List

// Importing ArrayList class from
// java.util package
import java.util.ArrayList;

// Class
public class GFG {

    // Mai driver method
    public static void main(String[] args)
    {
        // Creating an ArrayList object
        // (Declaring List of String type)
        ArrayList<String> names = new ArrayList<String>();

        // Adding (appending) elements to List
        // Custom inputs using add() method
        names.add("Computer");
        names.add("Science");
        names.add("Portal");

        // Printing all the elements of ArrayList
        // Declaring generic ArrayList of String type
        System.out.print(names);
    }
}
```

**Output**

```java
[Computer, Science, Portal]
```

**B)后半部分:**制作相同的数组列表，以类对象为元素。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to show
// How objects can an ArrayList hold

// Importing ArrayList class from
// java.util package
import java.util.ArrayList;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Make Person data-type objects
        Person p1 = new Person("Aditya", 19);
        Person p2 = new Person("Shivam", 19);
        Person p3 = new Person("Anuj", 15);

        // Create an ArrayList object
        //(Declaring List of Person type)
        ArrayList<Person> names = new ArrayList<Person>();

        // Adding objects to the ArrayList
        names.add(p1);
        names.add(p2);
        names.add(p3);

        // Print and display the elements of adobe ArrayList
        // using get() method
        System.out.println(names.get(0).name);
        System.out.println(names.get(0).age);
        System.out.println(names.get(1).name);
        System.out.println(names.get(1).age);
        System.out.println(names.get(2).name);
        System.out.println(names.get(2).age);

        // New Line
        System.out.println();

        // Optional Part for better understanding
        System.out.println(
            "Optional Part Added For Better Understanding");

        // (Optional)
        // Displaying what happens if printed by simply
        // passing List object as parameter
        System.out.println(names);
    }
}

// Class user-defined
class Person {

    // Random properties associated with the person
    // Person name
    String name;
    // Person age
    int age;

    // Constructor for class Person
    // for initializing objects
    Person(String name, int age)
    {
        // This keyword for efering to current object
        this.name = name;
        this.age = age;
    }
}
```

**Output**

```java
Aditya
19
Shivam
19
Anuj
15

Optional Part Added For Better Understanding
[Person@214c265e, Person@448139f0, Person@7cca494b]
```