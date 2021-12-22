# 将数组列表转换为 Java 中的 Vector

> 原文:[https://www . geesforgeks . org/convert-ArrayList-to-vector-in-Java/](https://www.geeksforgeeks.org/convert-arraylist-to-vector-in-java/)

有几种方法可以将[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)转换为[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)。我们可以使用向量构造函数将数组列表转换成向量。我们可以一个接一个地读取数组列表元素，并将它们添加到向量中。

**方法 1:(使用向量构造器)**

*   创建一个数组列表。
*   在数组列表中添加元素。
*   创建一个向量，并在向量构造函数中传递数组列表。

**向量(** [集合](https://www.geeksforgeeks.org/collection-interface-in-java-with-examples/) **c):** 创建包含集合 c 元素的向量

```
*Vector<E> v = new Vector<E>(Collection c);*
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert ArrayList to Vector

import java.util.ArrayList;
import java.util.Vector;

public class GFG {
    public static void main(String[] args)
    {

        // create ArrayList
        ArrayList<Integer> ArrList = new ArrayList<Integer>();

        // add elements in ArrayList
        ArrList.add(10);
        ArrList.add(20);
        ArrList.add(30);
        ArrList.add(40);
        ArrList.add(50);

        // display ArrayList
        System.out.println(" ArrayList : " + ArrList);

        // create vector and pass the ArrayList in vector
        // constructor
        Vector<Integer> vector = new Vector<Integer>(ArrList);

        // print vector
        System.out.println(" Vector : " + vector);
    }
}
```

**Output**

```
 ArrayList : [10, 20, 30, 40, 50]
 Vector : [10, 20, 30, 40, 50]
```

**方法 2:(使用** [进行循环](https://www.geeksforgeeks.org/java-for-loop-with-examples/) **)**

*   创建一个数组列表。
*   在数组列表中添加一些值。
*   创建一个矢量。
*   执行循环。
*   从左侧到右侧遍历数组列表的每个元素。
*   在向量中添加数组列表元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert ArrayList to Vector

import java.util.Vector;
import java.util.ArrayList;
public class GFG {
    public static void main(String[] args)
    {
        // Create a ArrayList that contain strings
        ArrayList<String> Arrlist = new ArrayList<String>();

        // add values in ArrayList
        Arrlist.add("A");
        Arrlist.add("B");
        Arrlist.add("C");
        Arrlist.add("D");
        Arrlist.add("E");

        // Display the ArrayList
        System.out.println(" ArrayList :  " + Arrlist);

        // create a vector
        Vector<String> v = new Vector<String>();

        // Convert ArrayList to Vector

        // get the size to AffayList
        int n = Arrlist.size();

        // execute for loop from 0 to n
        for (int i = 0; i < n; i++) {

            // get the elements from ArrayList
            // and add the arrayList elements in vector
            v.add(Arrlist.get(i));
        }

        // Display Vector
        System.out.println("\n vector : " + v);
    }
}
```

**Output**

```
 ArrayList :  [A, B, C, D, E]

 vector : [A, B, C, D, E]
```

**方法三:(使用**T2【addAll()T4【方法)

该方法用于将集合中作为参数传递给该函数的所有元素追加到向量的末尾，记住集合迭代器的返回顺序。

**语法:**

```
boolean addAll(Collection C)
```

**参数:**该方法接受一个强制参数 **C** ，它是数组列表的集合。它是一个集合，其元素需要追加到向量的末尾。

**返回值:**如果至少执行了一个追加动作，则该方法返回*真*，否则返回*假*。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert ArrayList to Vector

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        ArrayList<String> listStrings = new ArrayList<>();

        listStrings.add("Geeks");
        listStrings.add("for");
        listStrings.add("Geeks");

        // create empty vector object
        Vector<String> vStrings = new Vector<>();

        // use the addAll method
        vStrings.addAll(listStrings);

        System.out.println("Vector contains: " + vStrings);
    }
}
```

**Output**

```
Vector contains: [Geeks, for, Geeks]
```