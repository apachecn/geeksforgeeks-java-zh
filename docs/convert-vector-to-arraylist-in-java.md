# 将向量转换为 Java 中的数组列表

> 原文:[https://www . geesforgeks . org/convert-vector-to-ArrayList-in-Java/](https://www.geeksforgeeks.org/convert-vector-to-arraylist-in-java/)

有多种方法可以将向量转换为[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)，使用在数组列表构造函数中传递向量，以及使用简单的向量遍历和向数组列表添加值。

**方法 1:**

1.  Create a vector.
2.  Add some values to the Vector.
3.  Create a new array list.
4.  Traverse the vector from left to right.
5.  Start adding each element in the array list.

下面是上述方法的实现:

## Java

T0T6】

**时间复杂度:** O(n)

**方法 2:**

*   Create a vector.
*   Add some values to the Vector.
*   Create an array list and pass the vector in the array list constructor.

**语法:**

```java
ArrayList<String> ArrList = new ArrayList<String>(vector);
```

下面是上述方法的实现:

T3】JavaT5

```java
// Convert Vector to ArrayList in Java
import java.util.Vector;
import java.util.ArrayList;

public class GFG {

    public static void main(String[] args)
    {

        // Create a Vector that contain strings

        Vector<String> v = new Vector<String>();

        // add values in vector

        v.add("a");
        v.add("b");
        v.add("c");
        v.add("d");
        v.add("e");

        // Display the Vector

        System.out.println(" Vector :  " + v);

        // Convert Vector to ArrayList
        ArrayList<String> Arrlist
            = new ArrayList<String>(v);

        // Display ArrayList
        System.out.println("\n ArrayList : " + Arrlist);
    }
}
```

T6T8**输出**T1

**时间复杂度:** O(n)