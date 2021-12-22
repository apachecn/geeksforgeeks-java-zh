# 排序数组列表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-sort-an-ArrayList/](https://www.geeksforgeeks.org/java-program-to-sort-an-arraylist/)

数组列表是集合框架中提供的类。在 Java 中，集合框架是在 java.util 包中定义的。数组列表用于动态存储元素。它比数组更灵活，因为数组列表中没有大小限制。数组列表以无序的方式存储数据。在某些情况下，我们需要以有序的方式重新排列数据。

java 中有两种数组列表。一个是包装器类对象的数组列表，另一个是用户定义对象的数组列表。我们将看到这两种数组列表的排序。让我们从第一个开始。

1.  对包装类对象的数组列表进行排序。
    *   升序
    *   降序
2.  对用户定义对象的数组列表进行排序。
    *   可比较的
    *   比较仪

**类型 1:对包装类对象的数组列表进行排序**

包装器类对象的数组列表只不过是字符串、整数等对象的数组列表。数组列表可以按升序和降序两种方式排序。集合类提供了两种排序数组列表的方法。sort()和 reverseOrder()分别用于升序和降序。

**1(A)升序**

这个 sort()方法接受列表对象作为参数，它将返回一个按升序排序的数组列表。sort()方法的语法如下。

```
Collections.sort(objectOfArrayList);
```

数组列表中的所有元素必须相互可比较，否则会抛出 **ClassCastException** 。这里，相互可比较意味着列表中的所有项目具有相同的数据类型。

```
ArrayList<Integer> list = new ArrayList<Integer>();   
list.add(132);  
list.add(321);   
list.add("India");
```

在上面的例子中，我们看到一个列表有三个元素，其中两个元素是整数类型，一个是字符串类型。整数中的两个元素是相互可比较的，但是字符串类型的元素与其他两个元素不可比较。在这种情况下，我们可以得到一个 ClassCastException。因此，列表必须具有相同类型的元素。

让我们考虑下面的例子来理解排序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Sort an ArrayList

// import java.util package
import java.util.*;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Define an objects of ArrayList class
        ArrayList<String> list = new ArrayList<String>();

        // Adding elements to the ArrayList
        list.add("India");
        list.add("Pakistan");
        list.add("Srilanka");
        list.add("USA");
        list.add("Australia");
        list.add("Japan");

        // Printing the unsorted ArrayList
        System.out.println("Before Sorting : " + list);

        // Sorting ArrayList in ascending Order
        Collections.sort(list);

        // printing the sorted ArrayList
        System.out.println("After Sorting : " + list);
    }
}
```

**输出:**

```
Before Sorting : [India, Pakistan, Srilanka, USA, Australia, Japan]
After Sorting : [Australia, India, Japan, Pakistan, Srilanka, USA]
```

**1(B)降序**

为了按降序对数组列表进行排序，我们使用[***【reverse order()】***](https://www.geeksforgeeks.org/collections-reverseorder-java-examples/)方法作为 sort()方法的参数。我们不能直接调用 reverseOrder()方法。这个方法有两个参数，一个是数组列表的对象，第二个参数是 Collections.reversOrder()方法。此方法将按降序返回数组列表。类似于 sort()方法，ArrayList 必须是相互可比较的，否则会抛出 **ClassCastException** 。

```
Collections.sort(objectOfArrayList, Collections.reverseOrder());
```

这里，这个方法首先按升序对项目进行排序，然后它将颠倒排序项目的顺序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Sort an ArrayList

// Importing generic java files
import java.util.*;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Define an objects of ArrayList class
        ArrayList<Integer> list = new ArrayList<Integer>();

        // Adding elements to the ArrayList
        list.add(410);
        list.add(250);
        list.add(144);
        list.add(967);
        list.add(289);
        list.add(315);

        // Printing the unsorted ArrayList
        System.out.println("Before Sorting : " + list);

        // Sorting ArrayList in descending Order
        Collections.sort(list, Collections.reverseOrder());

        // Printing the sorted ArrayList
        System.out.println("After Sorting : " + list);
    }
}
```

**输出:**

```
Before Sorting : [410, 250, 144, 967, 289, 315]
After Sorting : [967, 410, 315, 289, 250, 144]
```

**2。对用户定义对象的数组列表进行排序**

用户定义对象的数组列表只不过是自定义对象的数组列表。在 Java 中，有两个接口可以用来对集合元素进行排序。可比和比较。

**2(A)可比**

Comparable 提供单一的排序顺序。如果我们使用 Comparable，它将影响原始类。可比接口提供 ***【比较】()*** 方法对元素进行排序。在 java 中，comparable 是由 java.lang 包提供的。我们可以通过调用 ***Collections.sort(List)方法*** 对数组列表进行排序。

**示例:**根据库存汽车数量进行排序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Sort an ArrayList

// Importing generic java files
import java.util.*;

// Implements comparable interface into custom class
class Car implements Comparable<Car> {
    int ModalNo;
    String name;
    int stock;

    // Parameterized constructor of the class
    Car(int ModalNo, String name, int stock)
    {
        this.ModalNo = ModalNo;
        this.name = name;
        this.stock = stock;
    }

    // Override the compareTo method
    public int compareTo(Car car)
    {
        if (stock == car.stock)
            return 0;
        else if (stock > car.stock)
            return 1;
        else
            return -1;
    }
}

// Main driver method
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create the ArrayList object
        ArrayList<Car> c = new ArrayList<Car>();
        c.add(new Car(2018, "Kia", 20));
        c.add(new Car(2020, "MG", 13));
        c.add(new Car(2013, "creta", 10));
        c.add(new Car(2015, "BMW", 50));
        c.add(new Car(2017, "Audi", 45));

        // Call the sort function
        Collections.sort(c);

        // Iterate over ArrayList using for each loop
        for (Car car : c) {

            // Print the sorted ArrayList
            System.out.println(car.ModalNo + " " + car.name
                               + " " + car.stock);
        }
    }
}
```

**输出:**

```
2013 creta 10
2020 MG 13
2018 Kia 20
2017 Audi 45
2015 BMW 50
```

**2(B)比较器**

比较器提供多种排序顺序。比较器不会影响原始类。比较器提供 **compare()** 方法对元素进行排序。在 java 中，comparable 由 java.util 包提供。我们可以通过调用 Collections.sort(List，Comparator)方法对数组列表进行排序。举个例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Sort an ArrayList

// Step 1: ImportingDB files
import java.util.*;

// Class 1: Parent Class
class Car {
    int ModalNo;
    String name;
    int stock;

    // Parameterized constructor
    Car(int ModalNo, String name, int stock)
    {
        this.ModalNo = ModalNo;
        this.name = name;
        this.stock = stock;
    }
}

// Class 2: Child class
// creates the comparator for comparing stock value
class StockComparator implements Comparator<Car> {

    // Function to compare
    public int compare(Car c1, Car c2)
    {
        if (c1.stock == c2.stock)
            return 0;
        else if (c1.stock > c2.stock)
            return 1;
        else
            return -1;
    }
}

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Create the ArrayList object
        ArrayList<Car> c = new ArrayList<Car>();
        c.add(new Car(2018, "Kia", 20));
        c.add(new Car(2020, "MG", 13));
        c.add(new Car(2013, "creta", 10));
        c.add(new Car(2015, "BMW", 50));
        c.add(new Car(2017, "Audi", 45));

        // Call the sort function
        Collections.sort(c, new StockComparator());

        // For each loop to iterate
        for (Car car : c) {

          // Print the sorted ArrayList
            System.out.println(car.stock + " " + car.name
                               + " " + car.ModalNo);
        }
    }
}
```

**输出:**

```
10 creta 2013
13 MG 2020
20 Kia 2018
45 Audi 2017
50 BMW 2015
```