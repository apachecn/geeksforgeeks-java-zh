# Java 中的集合交换()方法，示例

> 原文:[https://www . geesforgeks . org/collections-swap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-swap-method-in-java-with-examples/)

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

以下是说明*交换()*方法的示例

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// swap() method for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // creating object of List<String>
            List<String> vector = new ArrayList<String>();

            // populate the vector
            vector.add("A");
            vector.add("B");
            vector.add("C");
            vector.add("D");
            vector.add("E");

            // printing the vector before swap
            System.out.println("Before swap: " + vector);

            // swap the elements
            System.out.println("\nSwapping 0th and 4th element.");
            Collections.swap(vector, 0, 4);

            // printing the vector after swap
            System.out.println("\nAfter swap: " + vector);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("\nException thrown : " + e);
        }
    }
}
```

**Output:** 

```
Before swap: [A, B, C, D, E]

Swapping 0th and 4th element.

After swap: [E, B, C, D, A]
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
            vector.add("A");
            vector.add("B");
            vector.add("C");
            vector.add("D");
            vector.add("E");

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

**Output:** 

```
Before swap: [A, B, C, D, E]

Trying to swap elements more than upper bound index 
Exception thrown : java.lang.IndexOutOfBoundsException: Index: 5, Size: 5
```