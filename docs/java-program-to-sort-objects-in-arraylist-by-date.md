# 按日期对数组列表中的对象进行排序的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-按日期对数组列表中的对象进行排序/](https://www.geeksforgeeks.org/java-program-to-sort-objects-in-arraylist-by-date/)

最重要的工具是 sort()方法，该方法用于 Collections 类的比较器机制，按降序排序。是的，一般来说，如果我们想达到这个目标，考虑到边界条件，其中要排序的对象是用户定义的，然后盲目地使用比较器。下面讨论这两种方法，其中对象也是用户定义类型的。

**方法:**

在 Java 中，我们有多种方法可以按日期对数组列表中的对象进行排序。这可以通过使用**<>**界面或 **Collections.sort()** 方法来完成，要完成此任务，您可以使用其中任何一种方法。

1.  使用比较器接口
2.  使用 Collections.sort()方法

现在让我们一个一个地讨论它们。

**方法 1:** 使用比较器接口

Java **比较器**接口用于对用户定义类的对象进行排序。通过使用**比较器< >** 界面，您可以根据用户定义类中定义的任何数据成员对元素进行排序。 **java.util** 包包含这个接口。我们可以通过使用方法 [compare()](https://www.geeksforgeeks.org/how-compare-method-works-in-java/#:~:text=The%20compare()%20method%20in,%3A%20if%20(x%20%3C%20y)) 和 [compareTo()](https://www.geeksforgeeks.org/java-lang-string-compareto/) 来完成这个任务，它们将用于比较我们的 DateItem 类的对象。

**进场:**

*   创建一个新的类，并将该类命名为 **DateItem** ，并创建一个字符串类型的变量，然后创建一个 DateItem 类的构造函数，并将该字符串类型的变量传递到这里。
*   在**主**方法中，创建一个 DateItem 类型的数组列表。
*   将 DateItem 的对象存储在数组列表中。
*   创建另一个名为 **sortItems** 的类，它实现了**比较器**，并将我们的 DateItem 类传递给一个比较器。
*   现在在**比较器**类中创建一个比较方法，该方法返回一个整数，并将***【日期项目】***对象的两个参数作为**比较(对象 obj1，对象 obj2** )。****
*   ****在返回值的**比较**方法中，使用 ***比较()*** 方法，该方法将通过比较 DateItem 对象来返回指定的值。****
*   ****现在在**主**方法中使用 **Collections.sort()** 方法，将**数组列表**和“*sort item***”**类**对象**传递给它，它将对日期进行排序，并生成输出。****

******例 1******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java Program to Sort Objects in ArrayList by Date
// Using Comparator interface

// Importing required classes
import java.util.*;

// Class 1
// helper class for DateItem
class DateItem {

    // Member variable of this class
    String date;

    // Constructor of this class
    DateItem(String date)
    {

        // This keyword refers to current object itself
        this.date = date;
    }
}

// Class 2
// Helper class implementing Comparator
// from the Comparable interface
class sortItems implements Comparator<DateItem> {

    // Method of this class
    // @Override
    public int compare(DateItem a, DateItem b)
    {

        // Returning the value after comparing the objects
        // this will sort the data in Ascending order
        return a.date.compareTo(b.date);
    }
}

// Class 3
// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating ArrayList class object
        // Declaring object of type-DateItem
        // class(user-defined)
        ArrayList<DateItem> dateList = new ArrayList<>();

        // Adding data to the ArrayList
        // using standard add() method
        dateList.add(new DateItem("2020-03-25"));
        dateList.add(new DateItem("2019-01-27"));
        dateList.add(new DateItem("1998-01-27"));
        dateList.add(new DateItem("1998-02-26"));

        // Sorting the ArrayList
        // using Collections.sort() method
        Collections.sort(dateList, new sortItems());

        // Display message
        System.out.println("Sorted in Ascending Order");

        // Iterating the list using for-each loop
        for (DateItem d : dateList) {

            // Printing the sorted items from the List
            System.out.println(d.date);
        }
    }
}**
```

******Output**

```
Sorted in Ascending Order
1998-01-27
1998-02-26
2019-01-27
2020-03-25
```**** 

> ****注意:此代码将按升序对日期进行排序。如果您想更改排序顺序，可以参考以下程序:****

******例 2******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java Program to Sort Objects in ArrayList by Date
// Using Comparator interface

// Importing required classes
import java.util.*;

// Class 1
// Helper class
class DateItem {

    // Member variable
    String date;

    // Constructor of this class
    DateItem(String date)
    {

        // this keyword refers to current instance itself
        this.date = date;
    }
}

// Class 2
// Helper class implementing Comparable interface
class sortItems implements Comparator<DateItem> {
    // @Override

    // Method of this class
    // To compare datetime objects
    public int compare(DateItem a, DateItem b)
    {

        // Returning the value after comparing the objects
        // this will sort the data in Descending order
        return b.date.compareTo(a.date);
    }
}

// Class 3
// Main class
public class GFG {

    // Main driver method
    public static void main(String args[])
    {

        // Creating an ArrayList of DateItem class
        // (user-defined)
        ArrayList<DateItem> dateList = new ArrayList<>();

        // Adding data to the ArrayList
        // using standard add() method
        dateList.add(new DateItem("2020-03-25"));
        dateList.add(new DateItem("2019-01-27"));
        dateList.add(new DateItem("1998-01-27"));
        dateList.add(new DateItem("1998-02-26"));

        // Sorting the elements on ArrayList object above
        Collections.sort(dateList, new sortItems());

        // Display message only
        System.out.println("Sorted in Descending Order");

        // Iterating the List
        // using for-each loop
        for (DateItem d : dateList) {

            // Printing the sorted items from the List
            System.out.println(d.date);
        }
    }
}**
```

******Output**

```
Sorted in Descending Order
2020-03-25
2019-01-27
1998-02-26
1998-01-27
```**** 

******方法 2:** 使用 Collections.sort()方法****

****[*collections . sort()*](https://www.geeksforgeeks.org/collections-sort-java-examples/)方法可用于对自定义对象的数组列表进行排序。我们可以用这个方法按日期对数组列表中的对象进行排序。**java.util.Collections . sort()**方法存在于 Java . util . collections 类中。用于对集合的指定[列表](https://www.geeksforgeeks.org/list-interface-java-examples/)中的元素进行升序排序。它的工作原理类似于 [java.util.Arrays.sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 方法，但它比它更好，因为它可以对 Array 的元素以及链表、队列和其中更多的呈现进行排序。****

******例******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java Program to Sort Objects in ArrayList by Date
// Using Collections.sort() method

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an ArrayList of String to
        // store the Dates
        ArrayList<String> datesList = new ArrayList<>();

        // Adding date to ArrayList
        // using standard add() method
        datesList.add("2020-03-25");
        datesList.add("2019-01-27");
        datesList.add("2020-03-26");
        datesList.add("2020-02-26");

        // Display message only
        System.out.println(
            "Dates Object before sorting : ");

        // Iterating in the ArrayList
        // using for each loop
        for (String dates : datesList) {

            // Printing the data from the list
            System.out.println(dates);
        }

        // Sorting the ArrayList
        // using Collections.sort() method
        Collections.sort(datesList);

        // Display message only
        System.out.println("Dates Object after sorting : ");

        // Iterating in the ArrayList
        // using for-each loop
        for (String dates : datesList) {

            // Printing the data from the list
            System.out.println(dates);
        }
    }
}**
```

******Output**

```
Dates Object before sorting : 
2020-03-25
2019-01-27
2020-03-26
2020-02-26
Dates Object after sorting : 
2019-01-27
2020-02-26
2020-03-25
2020-03-26
```****