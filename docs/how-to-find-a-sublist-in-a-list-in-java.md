# 如何在 Java 中的列表中找到子列表？

> 原文:[https://www . geesforgeks . org/如何在 java 列表中找到子列表/](https://www.geeksforgeeks.org/how-to-find-a-sublist-in-a-list-in-java/)

**Java 中的列表**包含基于索引的方法。这使我们能够维护订单收集。因此，这使我们能够搜索、插入、删除甚至更新元素。这使我们能够存储列表中已经存在的同一元素的多个副本。此外，允许空元素成为列表的一部分。

我们通过名为“接口”的索引号来访问列表，这里就不讨论了。

**列表类型**

*   [阵列列表](https://www.geeksforgeeks.org/arraylist-in-java/)
*   链接列表
*   [堆叠](https://www.geeksforgeeks.org/stack-data-structure-introduction-program/)
*   向量

数组列表用于已知要插入的元素的地方，因为一旦我们声明了数组列表，就没有灵活性了，但是经常被使用，因为对元素的操作要快得多，数组列表的好的一面是我们可以通过数组**直接访问元素**是 t 接口。

**数组列表的语法:**

```java
ArrayList<String> cars = new ArrayList<String>();

```

**如果我们想要一个没有大小限制的灵活列表，并且对元素的操作非常慢，那么链接列表**比数组列表更受欢迎。

```java
LinkedList<E> extends AbstractList<E> implements List<E>, Deque<E> ;

```

**Vector** 方法类似于 ArrayList 只是 Vector 比 Arraylist 有优势，因为 Vector 中的所有元素都是同步的，只有在制作多线程应用程序时才有用。所以，在实践中，向量类并没有被更频繁地使用。

```java
Vector object= new vector(datatype parameter1, datatype parameter2, ...., datatype parameterN)

```

### 子列表是列表的一部分

**java.util.ArrayList** 类的 **subList()** 方法用于返回此列表中指定的 fromIndex(包含)和 toIndex(不包含)之间的部分的视图。

返回的列表由该列表支持，因此返回列表中的非结构性变化反映在该列表中，反之亦然。返回的列表支持所有可选的列表操作。

**语法:**

```java
public List subList(int fromIndex, int toIndex)

```

**参数:**该方法将以下参数作为参数。

*   **fromIndex:** 子列表的低端点(含)
*   **到索引:**子列表的高端点(不包括)

**返回类型:**该列表中指定范围的视图。

**异常:**此方法抛出如下异常。

*   **IndexOutOfBoundsException**–如果端点索引值超出范围(从索引大小开始)
*   **IllegalArgumentException**–如果端点索引无序(从索引>到索引)

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to find 
// Sublist in a List 
import java.util.*; 

public class GFG1 { 

    // Main Method
    public static void main(String[] argv) throws Exception 
    { 

        // Try block for exception
        try { 

            ArrayList<Integer> 
                arrlist = new ArrayList<Integer>(); 

            // Populating arrlist1 
            arrlist.add(1); 
            arrlist.add(4); 
            arrlist.add(9); 
            arrlist.add(25); 
            arrlist.add(36); 

            // Print arrlist 
            System.out.println("Original arrlist: "
                            + arrlist); 

            // Getting the subList 
            // using subList() method 
            List<Integer> arrlist2 = arrlist.subList(2, 4); 

            // Print the subList 
            System.out.println("Sublist of arrlist: "
                            + arrlist2); 
        } 

        // Catch block for exception
        catch (IndexOutOfBoundsException e) 
        { 
            System.out.println("Exception thrown : " + e); 
        } 

        // Catch block for exception
        catch (IllegalArgumentException e) 
        { 
            System.out.println("Exception thrown : " + e); 
        } 
    } 
}
```

**输出:**

```java
Original arrlist: [1, 4, 9, 25, 36]
Sublist of arrlist: [9, 25]

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find
// sublist in a List 

import java.util.*; 

public class GFG1 
{
    // Main Method 
    public static void main(String[] argv) throws Exception 
    { 
       // Exception try-catch block
        try { 

            ArrayList<String> arrlist = new ArrayList<String>(); 

            // Populating arrlist1 
            arrlist.add("Example"); 
            arrlist.add("in"); 
            arrlist.add("Geeks"); 
            arrlist.add("for"); 
            arrlist.add("Geeks"); 

            // print arrlist 
            System.out.println("Original arrlist: "
                            + arrlist); 

            // Getting the subList 
            // using subList() method 
            List<String> arrlist2 = arrlist.subList(2, 5); 

            // print the subList 
            System.out.println("Sublist of arrlist: "
                            + arrlist2); 
            } 

        // Exception try-catch block
        catch (IndexOutOfBoundsException e) 
        { 
            System.out.println("Exception thrown : " + e); 
        } 

        // Exception try-catch block
        catch (IllegalArgumentException e)
        { 
            System.out.println("Exception thrown : " + e); 
        } 
    } 
} 
```

**输出:**

```java
Original arrlist: [Example, in, Geeks, for, Geeks]
Sublist of arrlist: [Geeks, for, Geeks]

```

**示例 3:** 针对 IllegalArgumentException

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate 
// subList() method 
// for IllegalArgumentException 

import java.util.*; 

public class GFG1
{
    // Main Method
    public static void main(String[] argv) throws Exception 
    { 

        // Exception try-catch block
        try { 

            ArrayList<String> arrlist = new ArrayList<String>(); 

            // Populating arrlist1 
            arrlist.add("Example"); 
            arrlist.add("in"); 
            arrlist.add("Geeks"); 
            arrlist.add("for"); 
            arrlist.add("Geeks"); 

            // Print arrlist 
            System.out.println("Original arrlist: "
                            + arrlist); 

            // Getting the subList 
            // Using subList() method 
            System.out.println("\nEndpoint indices "
                            + "are out of order"
                            + " (fromIndex > toIndex)"); 
            List<String> arrlist2 = arrlist.subList(9, 3); 

            // print the subList 
            System.out.println("Sublist of arrlist: "
                            + arrlist2); 
             } 

        // Exception try-catch block
        catch (IndexOutOfBoundsException e) 
        { 
            System.out.println("Exception thrown: " + e); 
        } 

        // Exception try-catch block
        catch (IllegalArgumentException e) 
        { 
            System.out.println("Exception thrown: " + e); 
        } 

    } 

}
```

**输出:**

```java
Original arrlist: [Example, in, Geeks, for, Geeks]

Endpoint indices are out of order (fromIndex > toIndex)
Exception thrown: java.lang.IllegalArgumentException: fromIndex(9) > toIndex(3)

```

**示例 4:** 对于 IndexOutOfBoundsException

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate subList() 
// method for IndexOutOfBoundsException 

import java.util.*; 

public class GFG1 
{ 
    // Main Method
    public static void main(String[] argv) throws Exception 
    { 

        // Exception try-catch block
        try { 

            ArrayList<Integer> arrlist = new ArrayList<Integer>(); 

            // Populating arrlist1 
            arrlist.add(1); 
            arrlist.add(4); 
            arrlist.add(9); 
            arrlist.add(25); 
            arrlist.add(36); 

            // Print arrlist 
            System.out.println("Original arrlist: " + arrlist); 

            // Getting the subList 
            // Using subList() method 
            System.out.println("\nEnd index value is out of range"); 
            List<Integer> arrlist2 = arrlist.subList(2, 7); 

            // Print the subList 
            System.out.println("Sublist of arrlist: " + arrlist2); 
        } 

        // Exception try-catch block
        catch (IndexOutOfBoundsException e) 
        { 
            System.out.println("Exception thrown : " + e); 
        } 

        // Exception try-catch block
        catch (IllegalArgumentException e)
        { 
            System.out.println("Exception thrown : " + e); 
        } 

    } 

}
```

**输出:**

```java
Original arrlist: [1, 4, 9, 25, 36]

End index value is out of range
Exception thrown : java.lang.IndexOutOfBoundsException: toIndex = 7

```