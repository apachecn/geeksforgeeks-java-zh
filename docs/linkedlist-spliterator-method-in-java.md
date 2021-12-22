# Java 中的 LinkedList spliterator()方法

> 原文:[https://www . geesforgeks . org/linked list-spliterator-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-spliterator-method-in-java/)

**[链接列表](https://www.geeksforgeeks.org/linked-list-in-java/)** 的**拆分器()**方法返回一个 **[拆分器](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)** ，该拆分器是后期绑定的，并且使用与链接列表相同的元素快速失效。后期绑定拆分器绑定到元素源意味着在第一次遍历、第一次拆分或第一次查询估计大小时链接列表，而不是在创建拆分器时。它可以和 Java 8 中的 Streams 一起使用。此外，它还可以单独和批量遍历元素。Spliterator 是遍历元素的更好方法，因为它对元素提供了更多的控制。

**语法:**

```java
public Spliterator<E> spliterator()
```

**返回:**该方法在链表中的元素上返回一个**分割器**。

下面的程序说明了 LinkedList 的 spliterator()方法:

**示例 1:** 演示包含对象列表的 LinkedList 上的 spliterator()方法。

```java
// Java Program Demonstrate spliterator()
// method of LinkedList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an LinkedList which going to
        // contains a list of numbers
        LinkedList<Shape> shapes = new LinkedList<Shape>();

        // Add different shape to linkedlist
        shapes.add(new Shape("Circle", 234));
        shapes.add(new Shape("Square", 225));
        shapes.add(new Shape("Cone", 543));
        shapes.add(new Shape("Rectangle", 342));

        // create Spliterator of LinkedList
        // using spliterator() method
        Spliterator<Shape> spliter = shapes.spliterator();

        // print result from Spliterator
        System.out.println("list of Shapes:");

        // forEachRemaining method of Spliterator
        spliter.forEachRemaining((Value) -> printDetails(Value));
    }

    // print details
    public static void printDetails(Shape s)
    {
        System.out.println("************************");
        System.out.println("Shape Name : " + s.shapename);
        System.out.println("Shape Area : " + s.area);
    }
}

// create a shape class
class Shape {

    // shape class has two attributes
    String shapename;
    int area;

    public Shape(String shapename, int area)
    {
        super();
        this.shapename = shapename;
        this.area = area;
    }
}
```

**输出:**

```java
list of Shapes:
************************
Shape Name : Circle
Shape Area : 234
************************
Shape Name : Square
Shape Area : 225
************************
Shape Name : Cone
Shape Area : 543
************************
Shape Name : Rectangle
Shape Area : 342

```

**示例 2:** 演示包含电影名称列表的 LinkedList 上的 spliterator()方法。

```java
// Java Program Demonstrate spliterator()
// method of LinkedList

import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // create an LinkedList which going to
        // contains a list of Movie names which is actually
        // string values
        LinkedList<String> NameOfMovies = new LinkedList<String>();

        // Add Strings to list
        // each string represents city name
        NameOfMovies.add("Delhi 6");
        NameOfMovies.add("3 Idiots");
        NameOfMovies.add("Stree");
        NameOfMovies.add("Airlift");

        // using spliterator() method
        Spliterator<String> names = NameOfMovies.spliterator();

        // print result from Spliterator
        System.out.println("list of Movies:");

        // forEachRemaining method of Spliterator
        names.forEachRemaining((n) -> System.out.println("Movie Name: " + n));
    }
}
```

**输出:**

```java
list of Movies:
Movie Name: Delhi 6
Movie Name: 3 Idiots
Movie Name: Stree
Movie Name: Airlift

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/util/linkedlist . html # spliterator–](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html#spliterator--)