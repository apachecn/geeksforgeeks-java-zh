# 比较 Java 中的两个数组列表

> 原文:[https://www . geesforgeks . org/comparison-two-ArrayList-in-Java/](https://www.geeksforgeeks.org/comparing-two-arraylist-in-java/)

Java 提供了一种比较两个数组列表的方法。ArrayList.equals()是用于比较两个数组列表的方法。它将数组列表进行比较，因为两个数组列表的大小应该相同，并且两个数组列表中所有对应的元素对都是相等的。

**例:**

```java
Input : ArrayList1 = [1, 2, 3, 4],
        ArrayList2 = [1, 2, 3, 4]
Output: Array List are equal

Input : ArrayList1 = [1, 2, 3, 4],
        ArrayList2 = [4, 2, 3, 1]
Output: Array List are not equal
```

**语法:**

```java
boolean equals(Object o)
```

**参数:**该函数有一个参数，该参数是要进行相等比较的对象。

**返回:**如果数组列表相等，该方法返回真。

**实现:**

T5】Java

```java
// Comparing two ArrayList In Java
import java.util.ArrayList;

public class GFG {
    public static void main(String[] args)
    {

        // create two Array List
        ArrayList<String> ArrayList1
            = new ArrayList<String>();
        ArrayList<String> ArrayList2
            = new ArrayList<String>();

        // insert items in AyyarList 1
        ArrayList1.add("item 1");
        ArrayList1.add("item 2");
        ArrayList1.add("item 3");
        ArrayList1.add("item 4");

        // insert items in AyyarList 2
        ArrayList2.add("item 1");
        ArrayList2.add("item 2");
        ArrayList2.add("item 3");
        ArrayList2.add("item 4");

        // Display both ArrayList
        System.out.println(" ArrayList1 = " + ArrayList2);
        System.out.println(" ArrayList1 = " + ArrayList1);

        // compare ArrayList1 with ArrayList2
        if (ArrayList1.equals(ArrayList2) == true) {
            System.out.println(" Array List are equal");
        }
        else
        // else block execute when
        // ArrayList are not equal
        {
            System.out.println(" Array List are not equal");
        }

        // insert one more item in ArrayList 1
        System.out.println(
            "\n Lets insert one more item in Array List 1");
        ArrayList1.add("item 5");

        // display both ArrayList
        System.out.println(" ArrayList1 = " + ArrayList1);
        System.out.println(" ArrayList = " + ArrayList2);

        // again compare ArrayList 1 with ArrayList 2
        if (ArrayList1.equals(ArrayList2) == true) {
            System.out.println(" Array List are equal");
        }
        else {
            System.out.println(" Array List are not equal");
        }
    }
}
```

**输出**

```java
 ArrayList1 = [item 1, item 2, item 3, item 4]
 ArrayList1 = [item 1, item 2, item 3, item 4]
 Array List are equal

 Lets insert one more item in Array List 1
 ArrayList1 = [item 1, item 2, item 3, item 4, item 5]
 ArrayList = [item 1, item 2, item 3, item 4]
 Array List are not equal

```

**时间复杂度:** O(N)，其中 N 为数组列表的长度。