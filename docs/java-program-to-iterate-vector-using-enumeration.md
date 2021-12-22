# 使用枚举迭代向量的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-迭代-向量使用-枚举/](https://www.geeksforgeeks.org/java-program-to-iterate-vector-using-enumeration/)

[向量类](https://www.geeksforgeeks.org/java-util-vector-class-java/)实现了一个可增长的对象数组。它在 java.util 包中提供。它实现了列表接口。枚举接口定义了遍历对象集合中的元素的方法。现在为了添加元素

**向量语法:**

> 公共类向量<e>扩展抽象列表<e>实现列表<e>，随机访问，可克隆，可序列化</e></e></e>

[**Java . util . enumeration**](https://www.geeksforgeeks.org/enumeration-interface-in-java/)**接口是预定义的接口之一，其对象用于从 collections 框架变量中检索数据(如 [Stack](https://www.geeksforgeeks.org/stack-class-in-java/) 、 [Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 、 [HashTable](https://www.geeksforgeeks.org/hashtable-in-java/) 、等。)仅在向前的方向，而不在向后的方向。**

**可以使用 [Java.util.Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 。addElement()方法，通过将向量的大小增加 1，将指定的元素追加到该向量的末尾。这个方法的功能类似于 Vector 类的 add()方法。**

****语法:****

```java
boolean addElement(Object element)
```

****参数:**该函数接受对象类型的单个参数*元素*，并引用该参数指定的元素，该元素被附加到 ve **c** tor 的末尾。**

****返回值:**这是一个 void 类型的方法，不返回值。**

****例 1:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to Iterate Vector using Enumeration

// Importing Enumeration class
import java.util.Enumeration;

// Importing vector class
import java.util.Vector;

public class GFG {

    // Main driver method
    public static void main(String a[])
    {
        // Creating a new vector
        Vector<String> v = new Vector<String>();

        // Adding elements to the end
        v.add("Welcome");
        v.add("To");
        v.add("Geeks for");
        v.add("Geeks");

        // Creating an object of enum
        Enumeration<String> en = v.elements();

        while (en.hasMoreElements()) {

            // Print the elements using enum object
            // of the elements adeded in the vector
            System.out.println(en.nextElement());
        }
    }
}
```

****Output**

```java
Welcome
To
Geeks for
Geeks
```** 

****例 2:****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to Iterate Vector using Enumeration

// Importing Enumeration class
import java.util.Enumeration;
// Importing Vector class
import java.util.Vector;

public class GFG {

    // Main driver method
    public static void main(String a[])
    {

        // Creating a vector object
        Vector<Integer> v = new Vector<Integer>();

        // Adding elements to the end
        v.add(1);
        v.add(2);
        v.add(3);
        v.add(4);

        // Creating an enum object
        Enumeration<Integer> en = v.elements();

        while (en.hasMoreElements()) {

            // Displaying elements of vector class
            // calling enum object
            System.out.println(en.nextElement());
        }
    }
}
```

****Output**

```java
1
2
3
4
```**