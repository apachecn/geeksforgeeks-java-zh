# 如何在 Java 中给 TreeSet 添加自定义类对象？

> 原文:[https://www . geesforgeks . org/如何将自定义类对象添加到 java 树集中/](https://www.geeksforgeeks.org/how-to-add-custom-class-objects-to-the-treeset-in-java/)

[TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 是 java 中 [SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 接口的实现，使用[红黑树](https://www.geeksforgeeks.org/red-black-tree-set-1-introduction-2/)进行存储。默认情况下，它保持升序。它只包含独特的元素。它不允许空元素。存取和检索时间相当快。要将用户定义的对象添加到 TreeSet 中，我们需要实现一个可比较的接口。我们要在 TreeSet 中添加的元素必须是可比较的类型。如果我们不实现可比接口，那么它将抛出 **ClassCastException。**

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Importing util package
import java.util.*;

// Custome class Car implements Comparable interface
class Car implements Comparable<Car> {

    // attributes
    int Modelno;
    String name, city;
    int stock;

    // Car constructor
    public Car(int Modelno, String name, String city,
               int stock)
    {
        this.Modelno = Modelno;
        this.name = name;
        this.city = city;
        this.stock = stock;
    }

    // Override the compareTo() method
    public int compareTo(Car c)
    {
        if (stock > c.stock) {
            return 1;
        }
        else if (stock < c.stock) {
            return -1;
        }
        else {
            return 0;
        }
    }
}

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Define an objects of TreeSet class
        TreeSet<Car> set = new TreeSet<Car>();

        // Creating Car objects
        Car c1 = new Car(132, "BMW", "Rajkot", 35);
        Car c2 = new Car(269, "Audi", "Surat", 20);
        Car c3 = new Car(560, "Kia", "Vadodara", 15);
        Car c4 = new Car(109, "Creta", "Ahmedabad", 26);

        // Adding Car objects to TreeSet
        set.add(c1);
        set.add(c2);
        set.add(c3);
        set.add(c4);

        // Traversing TreeSet
        for (Car c : set) {
            System.out.println(c.stock + " " + c.name + " "
                               + c.city + " " + c.Modelno);
        }
    }
}
```

**Output**

```java
15 Kia Vadodara 560
20 Audi Surat 269
26 Creta Ahmedabad 109
35 BMW Rajkot 132

```

我们需要覆盖 **compareTo()** 方法，这样它就会按照特定的顺序对我们的集合进行排序。

**示例 2:** 让我们举同一个例子，但是现在我们针对汽车的名称覆盖了 compareTo()方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Importing util package
import java.util.*;

// Custome class Car implements Comparable interface
class Car implements Comparable<Car> {

    // attributes
    int Modelno;
    String name, city;
    int stock;

    // Car constructor
    public Car(int Modelno, String name, String city,
               int stock)
    {
        this.Modelno = Modelno;
        this.name = name;
        this.city = city;
        this.stock = stock;
    }

    // Override the compareTo() method
    public int compareTo(Car c)
    {
        return name.compareTo(c.name);
    }
}

public class GFG {
    // Main driver method
    public static void main(String[] args)
    {

        // Define an objects of TreeSet class
        TreeSet<Car> set = new TreeSet<Car>();

        // Creating Car objects
        Car c1 = new Car(132, "BMW", "Rajkot", 35);
        Car c2 = new Car(269, "Audi", "Surat", 20);
        Car c3 = new Car(560, "Kia", "Vadodara", 15);
        Car c4 = new Car(109, "Creta", "Ahmedabad", 26);

        // Adding Car objects to TreeSet
        set.add(c1);
        set.add(c2);
        set.add(c3);
        set.add(c4);

        // Traversing TreeSet
        for (Car c : set) {
            System.out.println(c.name + " " + c.stock + " "
                               + c.city + " " + c.Modelno);
        }
    }
}
```

**Output**

```java
Audi 20 Surat 269
BMW 35 Rajkot 132
Creta 26 Ahmedabad 109
Kia 15 Vadodara 560

```