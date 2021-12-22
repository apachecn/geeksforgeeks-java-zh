# 将数组转换为向量的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-转换-数组-向量/](https://www.geeksforgeeks.org/java-program-to-convert-array-to-vector/)

[数组](https://www.geeksforgeeks.org/arrays-in-java/)是一组相似类型的变量，由一个共同的名称引用。Java 数组可以是两种类型，即基元数据类型或类的对象(或非基元)引用。在原始数据类型的情况下，实际值存储在连续的内存位置，而在类的对象的情况下，实际对象存储在堆段中。

[Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 类实现了一个可增长的对象数组。兼容 [Java 集合](https://www.geeksforgeeks.org/collections-in-java-2/)。Vector 实现了一个动态数组，这意味着它可以根据需要增长或收缩。它包含可以使用整数索引(如数组)访问的组件。

**Java 中有 3 种方法可以将数组转换成向量。**

1.  使用 Collections.addAll 方法
2.  使用 Arrays.asList()方法
3.  使用循环

**方法 1:使用** [**集合**](https://www.geeksforgeeks.org/collections-addall-method-in-java-with-examples/) **方法**

**语法:**

```
public static boolean addAll(Collection c, T... elements)
```

**参数:**该方法采用以下参数作为参数

*   **c-** 要插入元素的集合
*   **元素-** 要插入 c 的元素

**返回值:**如果集合因调用而改变，则该方法返回 true。

**示例:**制作一个数组和一个空向量，在方法中传递填充的数组和空向量，向量将被数组元素填充。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert Array To Vector 
// Using Collections.addAll() method

import java.util.*;

public class array_to_vector {

    public static void main(String[] args)
    {

        String[] arr = { "I", "love", "geeks", "for", "geeks" };

        // create a new vector object of the same type
        Vector<String> v = new Vector<String>();

         // Use the addAll method of the Collections to add
         // all array elements to the vector object

        Collections.addAll(v, arr);

        System.out.println("The vector is");

        // printing vector
        System.out.println(v);
    }
}
```

**Output**

```
The vector is
[I, love, geeks, for, geeks]
```

**方法二:使用**[**array . aslist()**](https://www.geeksforgeeks.org/arrays-aslist-method-in-java-with-examples/)**方法**

**语法:**

```
public static List asList(T... a)
```

**参数:**该方法取**数组 a** ，需要转换为 List。

**示例:**Vector 构造函数可以取一个 List 对象，并将其转换为向量。因此，将数组转换为列表，并将其传递给向量构造函数。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert Array To Vector 
// Using Arrays.asList() method

import java.util.*;

public class array_to_vector {

    public static void main(String[] args)
    {

        String[] arr = { "I", "love", "geeks", "for", "geeks" };

        // create a new vector object of the same type
        Vector<String> v = new Vector<String>(Arrays.asList(arr));

        System.out.println("The vector is");

        // printing vector
        System.out.println(v);
    }
}
```

**Output**

```
The vector is
[I, love, geeks, for, geeks]
```

**方法 3:使用循环**

**示例:**循环遍历数组的每个元素，并在向量中逐个添加该元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Convert Array To Vector 
// Using simple iteration method

import java.util.*;

public class array_to_vector {

    public static void main(String[] args)
    {

        String[] arr = { "I", "love", "geeks", "for", "geeks" };

        // create a new vector object of the same type
        Vector<String> v = new Vector<String>();

        for (int i = 0; i < arr.length; i++)
            v.addElement(arr[i]);

        System.out.println("The vector is");

        // printing vector
        System.out.println(v);
    }
}
```

**Output**

```
The vector is
[I, love, geeks, for, geeks]
```