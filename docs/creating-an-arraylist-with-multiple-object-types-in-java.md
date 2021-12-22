# 在 Java 中创建具有多种对象类型的数组列表

> 原文:[https://www . geeksforgeeks . org/用 java 创建多对象类型数组列表/](https://www.geeksforgeeks.org/creating-an-arraylist-with-multiple-object-types-in-java/)

[ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 类 Java 基本上是一个可调整大小的数组，即它可以根据我们添加到其中的值动态地增长和收缩大小。它存在于 java.util 包中。

**语法:**创建整数类型的数组列表如下。

```java
List<Integer> list = new ArrayList <Integer>();
```

更常见的是创建一个确定类型的数组列表，如**整数，Double** 等。但是也有一种方法可以创建能够保存多种类型的**对象**的数组列表。

我们将讨论如何使用 [**对象**](https://www.geeksforgeeks.org/object-class-in-java/) 类来创建数组列表。

**对象**类是类层次结构的根。Java 中的每个类都在直接或间接地扩展它。如果一个类没有从任何其他类继承，那么它直接扩展对象类，否则如果它扩展任何类，那么它从它的基类间接扩展对象类。我们可以使用下面提到的语法使用**对象**类来声明我们的数组列表。

```java
ArrayList<Object> list = new ArrayList<Object>();
```

上面的列表可以保存任何类型的值。下面给出的代码给出了一个包含多种类型对象的数组列表的例子。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to create an ArrayList with
// Multiple Object Types in Java

import java.util.ArrayList;

public class GFG {
    public static void main(String[] args)
    {

        // Creating an ArrayList of Object type
        ArrayList<Object> arr = new ArrayList<Object>();

        // Inserting String value in arr
        arr.add("GeeksForGeeks");

        //  Inserting Integer value in arr
        arr.add(14);

        //  Inserting Long value in arr
        arr.add(1800L);

        // Inserting Double value in arr
        arr.add(6.0D);

        //  Inserting Float value in arr
        arr.add(1.99F);

        // arr after all insertions: ["GeeksForGeeks", 14,
        // 1800L, 6.0D, 1.99F]

        System.out.print(
            "ArrayList after all insertions: ");
        display(arr);

        // Replacing element at index 0 (i.e. an String)
        // with an Integer type value 50
        arr.set(0, 50);

        // Replacing element at index 1 (Integer value)
        // with a Double type value
        arr.set(1, 10.0D);

        // arr after modifications: [50, 10.0D,
        // 1800L, 6.0D, 1.99F]

        System.out.print("ArrayList after modifications: ");

        display(arr);
    }

    // Function to display elements of the ArrayList
    public static void display(ArrayList<Object> arr)
    {
        for (int i = 0; i < arr.size(); i++) {
            System.out.print(arr.get(i) + " ");
        }
        System.out.println();
    }
}
```

**Output**

```java
ArrayList after all insertions: GeeksForGeeks 14 1800 6.0 1.99 
ArrayList after modifications: 50 10.0 1800 6.0 1.99
```