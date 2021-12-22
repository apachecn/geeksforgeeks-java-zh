# Java 中数组列表的数组列表

> 原文:[https://www . geesforgeks . org/ArrayList-of-ArrayList-in-Java/](https://www.geeksforgeeks.org/arraylist-of-arraylist-in-java/)

我们已经讨论过数组列表的[数组在没有警告的情况下是不可能的。更好的方法是使用数组列表的数组列表。](https://www.geeksforgeeks.org/array-of-arraylist-in-java/)

```java
// Java code to demonstrate the concept of
// array of ArrayList

import java.util.*;
public class Arraylist {
    public static void main(String[] args)
    {
        int n = 3;

        // Here aList is an ArrayList of ArrayLists
        ArrayList<ArrayList<Integer> > aList = 
                  new ArrayList<ArrayList<Integer> >(n);

        // Create n lists one by one and append to the 
        // master list (ArrayList of ArrayList)
        ArrayList<Integer> a1 = new ArrayList<Integer>();
        a1.add(1);
        a1.add(2);
        aList.add(a1);

        ArrayList<Integer> a2 = new ArrayList<Integer>();
        a2.add(5);
        aList.add(a2);

        ArrayList<Integer> a3 = new ArrayList<Integer>();
        a3.add(10);
        a3.add(20);
        a3.add(30);
        aList.add(a3);

        for (int i = 0; i < aList.size(); i++) {
            for (int j = 0; j < aList.get(i).size(); j++) {
                System.out.print(aList.get(i).get(j) + " ");
            }
            System.out.println();
        }
    }
}
```

**Output:**

```java
1 2 
5 
10 20 30

```