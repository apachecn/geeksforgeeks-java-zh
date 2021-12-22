# 如何在 Java 中替换向量特定索引处的元素？

> 原文:[https://www . geeksforgeeks . org/如何替换 java 中矢量索引的特定元素/](https://www.geeksforgeeks.org/how-to-replace-an-element-at-a-specific-index-of-the-vector-in-java/)

这个 [**向量**](https://www.geeksforgeeks.org/java-util-vector-class-java/) 类实现了一个可生长的对象数组。向量基本上属于遗留类，但现在它与集合完全兼容。在 [**java.util 包**](https://www.geeksforgeeks.org/java-util-package-java/) 中找到，实现了 [List](https://www.geeksforgeeks.org/list-interface-java-examples/) 接口，所以我们可以在这里使用 List 接口的所有方法。

****例****

```java
Input  : Vector= ["Harry","Steve","Vince","David","Matt"],Index=1,Element ="Mark"
Output : Vector= ["Harry","Mark","Vince","David","Matt"]

Input  : Vector= ["Harry","Steve","Vince","David","Matt"],Index=2,Element ="Jack"
Output : Vector= ["Harry","Mark","Jack","David","Matt"]
```

**进场:**

向量中的一个元素可以在特定/指定的索引处用另一个元素替换，使用 [**set()方法**](https://www.geeksforgeeks.org/vector-set-method-in-java/)**或者我们可以说 java.util.Vector.set()方法。**

****语法:****

```java
Vector.set(int index, Object element)
```

****参数:**该函数接受两个强制参数，如上语法所示，如下所述。**

*   ****索引**:这是整型的，指的是向量中要替换的元素的位置。**
*   ****元素**:是替换现有元素的新元素，与矢量属于同一对象类型。**

****返回值:**该方法返回向量中被新值替换的前一个值。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to replace a element at a particular index
// in vector

import java.util.Vector;
public class GFG {
    public static void main(String[] args)
    {
        // making a new vector object
        Vector<String> vector = new Vector<String>();

        // adding elements to the vector.
        vector.add("Harry");
        vector.add("Steve");
        vector.add("Vince");
        vector.add("David");
        vector.add("Matt");

        System.out.println("Vector elements before replacement: ");

        for (int i = 0; i < vector.size(); i++) 
        {
            System.out.print(vector.get(i) + " ");
        }

        System.out.println();

        // Replacing index 1 element
        vector.set(1, "Mark");
        // Replacing index 2 element
        vector.set(2, "Jack");

        System.out.println("Vector elements after replacement: ");

        for (int i = 0; i < vector.size(); i++) 
        {
            System.out.print(vector.get(i) + " ");
        }

        System.out.println();
    }
}
```

****Output**

```java
Vector elements before replacement: 
Harry Steve Vince David Matt 
Vector elements after replacement: 
Harry Mark Jack David Matt 
```**