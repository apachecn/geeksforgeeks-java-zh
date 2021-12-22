# 在 Java 中迭代向量元素

> 原文:[https://www . geesforgeks . org/iterate-over-vector-elements-in-Java/](https://www.geeksforgeeks.org/iterate-over-vector-elements-in-java/)

**Vector** 就像是动态数组，可以增长也可以收缩它的大小。与数组不同，我们可以在其中存储 n 个元素，因为没有大小限制。

**我们可以通过以下方式迭代向量:**

*   简单 for 循环
*   增强的 for 循环
*   迭代程序
*   枚举接口

**方法一:简单** [**为-循环**](https://www.geeksforgeeks.org/loops-in-java/)

*   这个想法是运行一个 for 循环从开始直到向量的大小。
*   我们也可以从 n-1 迭代到 0，以逆序遍历。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Iterate over Vector elements

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating Vector object of type String
        Vector<Integer> v = new Vector<Integer>();

        // Adding elements to Vector object
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);
        v.add(60);
        v.add(70);

        System.out.print("The vector V is: ");

        // Print the vector
        for (Integer i = 0; i < v.size(); i++)
        {
            System.out.print(v.get(i) + " ");
        }
    }
}
```

**Output**

```java
The vector V is: 10 20 30 40 50 60 70 
```

**方法 2:增强 for-loop**

*   增强的 for 循环是 for 循环的高级版本。
*   在这种方法中，我们在循环中取两个参数，一个是变量，它将一个接一个地存储向量中的值，另一个是向量的名称。
*   变量访问我们向量的所有值。我们不能在增强 for 循环中修改我们的向量。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Iterate over Vector elements

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating Vector object of type String
        Vector<Integer> v = new Vector<Integer>();

        // Adding elements to Vector object
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);
        v.add(60);
        v.add(70);

        System.out.print("The vector V is: ");

        // Print the vector
        // x one by one holds all the values of our vector
        // till it reaches the end
        for (Integer x : v) {
            System.out.print(x + " ");
        }
    }
}
```

**Output**

```java
The vector V is: 10 20 30 40 50 60 70 
```

**方法三:使用** [**迭代器**](https://www.geeksforgeeks.org/iterators-in-java/)

*   迭代器是使用任何集合的非常强大的工具。
*   我们创建一个集合接口的迭代器，并使它指向向量的开头。
*   运行 while 循环，直到迭代器没有到达终点。
*   我们使用 ***hasNext()*** 来检查下一个值是否存在。
*   我们通过 ***下一步()*** 功能打印数值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Iterate over Vector elements

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating Vector object of type String
        Vector<Integer> v = new Vector<Integer>();

        // Adding elements to Vector object
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);
        v.add(60);
        v.add(70);

        System.out.print("The vector V is: ");

        // Print the vector
        // Take a iterator pointing to begin
        Iterator<Integer> itr = v.iterator();

        // Check until iterator has not reached end
        while (itr.hasNext())
        {
            System.out.print(itr.next() + " ");
        }
    }
}
```

**Output**

```java
The vector V is: 10 20 30 40 50 60 70 
```

**方法四:使用** [**枚举界面**](https://www.geeksforgeeks.org/enumeration-interface-in-java/)

*   我们也可以使用枚举接口来遍历我们的向量。
*   它使用*****hasmorelements()***函数检查我们的向量是否有更多的元素。**
*   **直到到达空值，它使用 ***hasnextElement()*** 方法打印值。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to iterate oer vector elements

import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating Vector object of type String
        Vector<Integer> v = new Vector<Integer>();

        // Adding elements to Vector object
        v.add(10);
        v.add(20);
        v.add(30);
        v.add(40);
        v.add(50);
        v.add(60);
        v.add(70);

        System.out.print("The vector V is: ");

        // Print the vector
        // Get all the vector elements into enumaeration
        Enumeration<Integer> e = v.elements();

        // Iterate until the last element
        while (e.hasMoreElements())
        {
            System.out.print(e.nextElement() + " ");
        }
    }
}
```

****Output**

```java
The vector V is: 10 20 30 40 50 60 70 
```**