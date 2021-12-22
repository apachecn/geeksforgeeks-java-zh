# 通过 Java 向量获取枚举

> 原文:[https://www . geesforgeks . org/get-enumeration-over-Java-vector/](https://www.geeksforgeeks.org/get-enumeration-over-java-vector/)

在 java 中，[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)是一个典型的动态数组，其大小可以增加或减少。在数组中，声明后不能更改大小。我们必须包含文件导入 [java.util.Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 来使用 Vector 并在其中存储值。另外，导入 [java.util.Enumeration](https://www.geeksforgeeks.org/collections-enumeration-method-in-java-with-examples/) 使用枚举。

**进场 1:集合**

在 Java Enumeration 类中，默认情况下，所有列出的常量都是公共的、静态的和最终的。创建向量后，**枚举()**方法获取向量上的枚举。

> **公共静态< T >枚举<对象>枚举(集合<对象> c)**
> 
> 是**公共类 Collections 扩展对象**的成员函数。

**枚举()**方法返回指定集合上的枚举对象，这里指定的集合是一个**向量**。在通过**向量**获得枚举对象之后，我们将使用[**hasmorelements()**](https://www.geeksforgeeks.org/enumeration-hasmoreelements-method-in-java-with-examples/)**和[**nextElement()**](https://www.geeksforgeeks.org/enumeration-nextelement-method-in-java-with-examples/)方法通过**向量**进行枚举。**

**下面是给定方法的实现:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Get Enumeration over Java Vector
import java.util.Collections;
import java.util.Enumeration;
import java.util.Vector;

class GFG {
    public static void main(String[] args)
    {
        // creating an object of Vector class
        Vector<String> vector = new Vector<>();

        // Adding elements to the Vector
        vector.add("Let's");
        vector.add("learn");
        vector.add("java");
        vector.add("from");
        vector.add("GFG");

        // printing the elements of the vector
        System.out.println(
            "The elements of the Vector is : " + vector);

        // getting the Enumeration object over Vector
        // the specified collection.
        Enumeration enumeration
            = Collections.enumeration(vector);

        // Now printing each enumeration constant
        // by enumerating through the Vector.
        System.out.println(
            "printing each enumeration constant by enumerating through the Vector:");
        while (enumeration.hasMoreElements()) {
            System.out.println(enumeration.nextElement());
        }
    }
}
```

****Output**

```
The elements of the Vector is : [Let's, learn, java, from, GFG]
printing each enumeration constant by enumerating through the Vector:
Let's
learn
java
from
GFG
```** 

****时间复杂度:** O(N)，其中 N 为向量的长度。**

****方法 2:****

1.  **我们将声明 Vector 对象，然后使用 v.add()向向量添加元素。**
2.  **使用 hasMoreElements()，然后使用 nextElement()显示对象。**

****方法使用:****

1.  **[**hasmorelements()**](https://www.geeksforgeeks.org/enumeration-hasmoreelements-method-in-java-with-examples/)**:**用来枚举元素是否多。**
2.  **[**【next elements()**](https://www.geeksforgeeks.org/enumeration-nextelement-method-in-java-with-examples/)**:用于返回枚举中的下一个对象。****

**下面是给定方法的实现:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
// Get Enumeration over Java Vector
import java.io.*;
import java.util.Enumeration;
import java.util.Vector;

class GFG {
    public static void main(String[] args)
    {

        Vector<Integer> v = new Vector<Integer>();

        // v.add() is used to add elements to the vector
        v.add(1);
        v.add(2);
        v.add(3);
        v.add(4);
        // Create Enumeration
        Enumeration e = v.elements();

        // hasMoreElements() is used to check whether there
        // are more element to be enumerated
        while (e.hasMoreElements()) {

            // nextElement() is used to return the next
            // object in enumeration
            System.out.println(e.nextElement());
        }
    }
}
```

****Output**

```
1
2
3
4
```** 

****时间复杂度:** O(N)，其中 N 为向量的长度。**