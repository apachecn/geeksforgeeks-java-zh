# 如何在 Java 中从向量中获取第一个和最后一个元素？

> 原文:[https://www . geesforgeks . org/如何从 java 矢量中获取第一个和最后一个元素/](https://www.geeksforgeeks.org/how-to-get-first-and-last-element-from-the-vector-in-java/)

向量中的第一个元素可以使用表示 util 包的向量类的 ***firstElement()方法*** 获得。向量中的最后一个元素可以使用向量类的 ***【最后一个元素】()方法*** 获得，该方法也代表 util 包。这两种方法都不需要任何参数。

*可以通过两种方式提取向量的第一个和最后一个元素:*

1.  Get the elements at the 0th index and the size-1 index directly by the get () method.
2.  贺盛瑞的第一个元素()。

**方法 1:获取第 0 个和最后一个索引的元素**

我们可以使用 get()方法:

*   For the first element, get the element at index 0.
*   For the last element, get the element at the (vector size -1) th index.

## Java

```
// Java program to get the first and
// last element of vector

import java.util.Vector;

public class Example {

    public static void main(String args[])
    {

        // Create instance of Vector class.

        Vector<Integer> vector = new Vector<>();

        // Add some Element in Vector

        vector.add(5);

        vector.add(9);

        vector.add(0);

        vector.add(5);

        vector.add(3);

        System.out.println("The Vector Elements are: "
                           + vector);

        System.out.println(
            "The First Element of the Vector is : "
            + vector.get(0));

        System.out.println(
            "The Last Element of the Vector is : "
            + vector.get(vector.size() - 1));
    }
}
```

**输出**

```
The Vector Elements are: [5, 9, 0, 5, 3]
The First Element of the Vector is : 5
The Last Element of the Vector is : 3
```