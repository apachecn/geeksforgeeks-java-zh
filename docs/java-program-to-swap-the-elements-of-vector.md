# 交换向量元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-swap-the-elements-of-vector/](https://www.geeksforgeeks.org/java-program-to-swap-the-elements-of-vector/)

**java.util.Collections** 类的 **swap()** 方法用于交换指定列表中指定位置的元素。如果指定的位置相等，调用此方法将保持列表不变。

**语法:**

```
public static void swap(List list, int i, int j)
```

**参数:**该方法将以下参数作为参数

*   **列表–**交换元素的列表。
*   **I–**要交换的一个元素的索引。
*   **j–**要交换的另一个元素的索引。

**异常**如果 I 或 j 超出范围(i = list.size() || j = list.size())，此方法将抛出**indexout of boundsexception**。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Swap Elements of Java Vector

import java.util.Collections;
import java.util.Vector;

public class GFG {
    public static void main(String[] args)
    {

        // create vector
        Vector<String> vector = new Vector<String>();

        // insert elements in vector
        vector.add("A");
        vector.add("B");
        vector.add("C");
        vector.add("D");
        vector.add("E");

        // print original vector
        System.out.println("Before Swapping = "+vector);

        // call Collection.swap() method
        Collections.swap(vector, 0, 4);

        // print vector after swap two elements
        System.out.println("After Swapping = "+vector);
    }
}
```

**Output**

```
[A, B, C, D, E]
After swapping
[E, B, C, D, A]
```

**示例 2:** 适用于*指数出界异常*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// swap() method for IndexOutOfBoundsException

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of List<String>
            List<String> vector = new ArrayList<String>();

            // populate the vector
            vector.add("rohan");
            vector.add("manish");
            vector.add("simran");
            vector.add("ananya");
            vector.add("ishika");

            // printing the vector before swap
            System.out.println("Before swap: " + vector);

            // swap the elements
            System.out.println("\nTrying to swap elements"
                               + " more than upper bound index ");
            Collections.swap(vector, 0, 5);

            // printing the vector after swap
            System.out.println("After swap: " + vector);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output**

```
Before swap: [rohan, manish, simran, ananya, ishika]

Trying to swap elements more than upper bound index 
Exception thrown : java.lang.IndexOutOfBoundsException: Index 5 out of bounds for length 5
```