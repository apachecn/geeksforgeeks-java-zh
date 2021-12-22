# Java 程序访问列表的一部分作为列表

> 原文:[https://www . geesforgeks . org/Java-程序访问列表中的列表部分作为列表/](https://www.geeksforgeeks.org/java-program-to-access-the-part-of-list-as-list/)

列表是存储在一起形成集合的有序元素序列。列表可以包含重复条目，也可以包含空条目。列表允许我们执行基于索引的操作，即添加、删除、操作和位置访问。Java 提供了一个内置接口<<java.util>>来执行列表以及其他基于类的功能。</java.util>

**方法:**

1.  维护开始和结束索引的简单方法。
2.  使用 [*子列表()*](https://www.geeksforgeeks.org/arraylist-sublist-method-in-java-with-examples/) 方法。

**方法 1**

1.  元素在列表所需的索引处被访问。
2.  将它们添加到新创建的空列表中。
3.  开始和结束索引值用于访问所需的列表部分。默认情况下，索引假定从 0 开始。

这种方法需要额外的空间来维护新的列表，以存储所需的子列表。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Access the Part of List as List

// Importing utility and input/output java classes
import java.util.*;
import java.io.*;
// Importing Iterator class
import java.util.Iterator;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring a list
        List<Integer> list1 = new ArrayList<Integer>();

        // Adding elements to list1
        list1.add(1);
        list1.add(7);
        list1.add(8);
        list1.add(2);
        list1.add(11);
        list1.add(3);
        list1.add(66);
        list1.add(30);

        // Print the original List
        System.out.println("The original list contents : ");

        Iterator iterator = list1.iterator();

        // Iterating over elements using hasNext()
        // which holds true till
        // there is further more element in the List
        while (iterator.hasNext()) {
            System.out.print(iterator.next() + " ");
        }

        // Declaring a new List to store sublist
        List<Integer> new_list = new ArrayList<Integer>();

        // Maintaining and Setting counter to zero
        int i = 0;

        // Specifying the positions of the list to access
        // custom
        int start_indx = 2, end_indx = 5;

        // Condition check which holds true till
        // current counter value is less than size of List
        while (i < list1.size()) {

            // Checking if counter is in range of start and
            // end indx
            if (i >= start_indx && i <= end_indx) {

                // Adding element to new List
                new_list.add(list1.get(i));
            }

            // Incrementing counter
            i++;
        }

        // Print all element of List
        System.out.println();

        // Display message
        System.out.println("The sublist contents : ");

        // Iterator
        iterator = new_list.iterator();

        // Iterating over elements using hasNext() method
        // which holds true till further element is
        // remaining in List else returns false
        while (iterator.hasNext()) {

            // Print the elements of subList
            System.out.print(iterator.next() + " ");
        }
    }
}
```

**Output**

```java
The original list contents : 
1 7 8 2 11 3 66 30 
The sublist contents : 
8 2 11 3
```

> 时间复杂度= 0(n)
> 
> 空间复杂度= 0(n)，其中 n 是列表的大小。

**方法 2:** Java 为我们提供了一个内置的方法[子列表()](https://www.geeksforgeeks.org/arraylist-sublist-method-in-java-with-examples/)来访问属于指定范围的索引值的元素。该方法由数组列表包提供。

**语法:**

```java
public List subList(int fromIndex, int toIndex)
```

**参数:**

*   fromIndex =开始索引
*   toIndex = endIndex

**返回类型:**所需元素的列表。该方法访问从 Index 到 toIndex-1 范围内的所有元素。如果 fromIndex 等于 toIndex，则返回一个空列表。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Access the Part of List as List

// Importing java utility package, and
// all classes of input/output library
import java.util.*;
import java.util.Iterator;
import java.io.*;

class AccessSublist {

    // Main driver method
    public static void main(String[] args)
    {

        // Declaring a List of String type
        List<String> list1 = new ArrayList<String>();

        // Adding elements to above List(List1)
        // Custom inputs
        list1.add("Are");
        list1.add("you");
        list1.add("working!");
        list1.add("hard");
        list1.add("Geeeks?");

        // Display message
        System.out.print("The original list contents : ");

        // Iterator
        Iterator iterator = list1.iterator();

        // Iterating over elements using hasNext()
        // which holds true till there is
        // further more element present in List
        while (iterator.hasNext()) {

            // Print the original List
            System.out.print(iterator.next() + " ");
        }

        // Extracting the contents of the list
        // index between 0 and 2 (custom)
        List<String> new_list = list1.subList(0, 3);

        // Print
        System.out.println();

        // Display message
        System.out.print("The sublist contents : ");

        // Iterator
        iterator = new_list.iterator();

        // Iterating over elements using hasNext()
        // which holds true till there is
        // further more element present in List
        while (iterator.hasNext()) {

            // Print the sublist(list2)
            System.out.print(iterator.next() + " ");
        }
    }
}
```

**Output**

```java
The original list contents : Are you working! hard Geeeks? 
The sublist contents : Are you working!
```