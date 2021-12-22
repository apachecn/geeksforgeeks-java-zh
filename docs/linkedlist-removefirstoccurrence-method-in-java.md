# Java 中的 linked list removefirst occurrence()方法

> 原文:[https://www . geesforgeks . org/linked list-removefirst occurrence-method-in-Java/](https://www.geeksforgeeks.org/linkedlist-removefirstoccurrence-method-in-java/)

Java . util . linkedlist . removefirst occurrence()用于从列表中移除指定元素的第一个匹配项。如果指定的元素没有出现，列表保持不变。

**语法**:

```
LinkedListObject.removeFirstOccurrence(Object element)
```

**参数:**该方法取一个参数*元素*，从列表中删除。对象类型应该与列表中的元素相同。
**返回值:**如果列表包含指定的元素并被删除，则该方法返回布尔值 True，否则返回 false。
以下程序说明了 removeFirstOccurrence()方法:
**程序 1 :**

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java code to demonstrate removeFirstOccurrence() method
import java.util.LinkedList;
public class GfG {
    // Main method
    public static void main(String[] args)
    {

        // Creating a LinkedList object
        LinkedList<String> list = new LinkedList<String>();

        // Adding an element at the last
        list.addLast("one");

        // Adding an element at the last
        list.addLast("two");

        // Adding an element at the last
        list.addLast("three");

        // Adding an element at the last
        list.addLast("one");

        System.out.print("List before removing the "+
                   "first Occurrence of \"one\" : ");

        // Printing the list
        System.out.println(list);

        // Removing first occurrence of one.
        boolean returnValue = list.removeFirstOccurrence("one");

        // Printing the returned value
        System.out.println("Returned Value : " + returnValue);

        System.out.print("List after removing the"+
                            " first Occurrence of \"one\" : ");

        // Printing the list
        System.out.println(list);
    }
}
```

**Output:** 

```
List before removing the first Occurrence of "one" : [one, two, three, one]
Returned Value : true
List after removing the first Occurrence of "one" : [two, three, one]
```

**程序 2 :**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to demonstrate removeFirstOccurrence method in LinkedList

import java.util.LinkedList;

public class GfG {
    // Main method
    public static void main(String[] args)
    {

        // Creating a LinkedList object
        LinkedList<Integer> list = new LinkedList<Integer>();

        // Adding an element at the last
        list.addLast(10);

        // Adding an element at the last
        list.addLast(20);

        // Adding an element at the last
        list.addLast(30);

        // Adding an element at the last
        list.addLast(10);

        System.out.print("List before removing the"+
                  " first Occurrence of \"10\" : ");

        // Printing the list
        System.out.println(list);

        // Removing first occurrence of one.
        boolean returnValue = list.removeFirstOccurrence(10);

        // Printing the returned value
        System.out.println("Returned Value : " + returnValue);

        System.out.print("List after removing the"+
                           " first Occurrence of \"10\" : ");

        // Printing the list
        System.out.println(list);
    }
}
```

**Output:** 

```
List before removing the first Occurrence of "10" : [10, 20, 30, 10]
Returned Value : true
List after removing the first Occurrence of "10" : [20, 30, 10]
```