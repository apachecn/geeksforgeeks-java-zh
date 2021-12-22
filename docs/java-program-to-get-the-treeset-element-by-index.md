# 通过索引获取树集合元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-the-treeset-by-element-index/](https://www.geeksforgeeks.org/java-program-to-get-the-treeset-element-by-index/)

**TreeSet** 是 **Java** 中 SortedSet 接口最重要的实现之一，它使用一棵树进行存储。无论是否提供显式比较器，元素的顺序都是由一个集合使用它们的自然顺序来维护的。

我们在树集中有元素，我们希望使用索引打印树集中的元素。

```java
TreeSet<Integer> set = new TreeSet();
set.add(2);
set.add(3);
set.add(9);
set.add(5);

// TreeSet always used to get prevent
// from the duplicates in the increasing order
Set Contains -> [2,3,5,9] 
```

所以，我们有集合中的元素-> [2，3，5，9]。现在我们不能直接访问元素，所以要访问元素，我们需要将集合转换为数组或列表来访问元素。

**所以通过索引获取元素的方法有很多:**

1.  通过遍历整个树集并将元素逐个添加到数组中，将树集转换为数组。
2.  使用将 TreeSet 转换为数组。toArray()方法。
3.  将 TreeSet 转换为数组列表。

**方法一:简单的将树集合转换成数组**

*   我们只需创建一个空数组。
*   我们遍历给定的集合，一个接一个地向数组中添加元素

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Get the TreeSet Element By Index

import java.io.*;
import java.util.*;
class GFG {

    public static void main (String[] args) {

        TreeSet<Integer> s = new TreeSet<Integer>(); 
        s.add(2);
          s.add(3);
          s.add(9);
          s.add(5);

        int n = s.size(); 
        int arr[] = new int[n]; 

        int i = 0; 

        // using for-each loop to traverse through 
        // the set and adding each element to array
        for (int ele : s) 
            arr[i++] = ele; 

        for(int res : arr)
        {
            System.out.print(res+ " ");
        }

      System.out.println();

      // getting the element at index 2
      System.out.print(arr[2]);
    }
}
```

**Output**

```java
2 3 5 9 
5
```

**方法二:使用。toArray()方法**

*   首先使用将集合转换为数组。toArray()方法。
*   并通过索引从数组中访问元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Get the TreeSet Element By Index

import java.io.*;
import java.util.*;
class GFG {
    public static void main (String[] args) {

        TreeSet<Integer> s = new TreeSet<Integer>(); 
        s.add(2);
          s.add(3);
          s.add(9);
          s.add(5);

        int n = s.size(); 
        Integer arr[] = new Integer[n]; 

        // .toArray() method converts the
        // set s to array here
        arr = s.toArray(arr); 

        for(int ele : arr)
        {
            System.out.print(ele+" ");
        }

          System.out.println();

        // getting the element at index 2
          System.out.print(arr[2]);

    }
}
```

**Output**

```java
2 3 5 9 
5
```

**方法 3:转换为数组列表**

*   首先通过直接使用构造函数将集合转换为列表。
*   然后通过索引从列表中获取元素

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Get the TreeSet Element By Index

import java.io.*;
import java.util.*;
class GFG {
    public static void main (String[] args) {

        TreeSet<Integer> s = new TreeSet<Integer>(); 
        s.add(2);
          s.add(3);
          s.add(9);
          s.add(5);

        int n = s.size(); 

        // this constructor converts directly 
        // the whole TreeSet to list
        List<Integer> list= new ArrayList<Integer>(s);

        for(int ele : list){
            System.out.print(ele+" ");
        }

          System.out.println();

        // getting the element at index 2
          System.out.print(list.get(2));

    }
}
```

**Output**

```java
2 3 5 9 
5
```