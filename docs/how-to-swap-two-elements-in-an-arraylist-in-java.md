# 如何在 Java 中交换数组列表中的两个元素？

> 原文:[https://www . geesforgeks . org/如何在 java 中交换数组列表中的两个元素/](https://www.geeksforgeeks.org/how-to-swap-two-elements-in-an-arraylist-in-java/)

我们可以使用 [Collections.swap()](https://www.geeksforgeeks.org/collections-swap-method-in-java-with-examples/) 方法交换数组列表的两个元素。此方法接受三个参数。第一个参数是[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)，另外两个参数是元素的索引。此方法不返回任何内容。

**语法:**

> 公共静态无效交换(列表列表，int a，int b)；

**参数**

*   **列表**:一个**数组列表**或者任意一个[列表](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/list-interface-java-examples/&sa=U&ved=2ahUKEwjF1bf5kKDtAhVM73MBHaYIDKYQFjAAegQIBhAB&usg=AOvVaw06UjhpHLp76nyOuDavxZ7l)实现类，其中元素被交换
*   **a:** 第一个元素的索引
*   **b** :第二个元素的索引

**异常:**如果数组列表的索引小于 0 或大于数组列表的大小，它将抛出**indexout of boundsexception**。

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to swap two elements in an ArrayList

import java.util.ArrayList;
import java.util.Collections;

public class GFG {

    public static void main(String a[])
    {

        // Create the Array List
        ArrayList<String> ArrList = new ArrayList<String>();

        // add the values in Array List
        ArrList.add("Item 1");
        ArrList.add("Item 2");
        ArrList.add("Item 3");
        ArrList.add("Item 4");
        ArrList.add("Item 5");

        // display Array List before swap
        System.out.println("Before Swap the ArrayList ");
        System.out.println(ArrList);

        // Swapping the elements at 1 and 2 indices
        Collections.swap(ArrList, 1, 2);

        // display Array List after swap
        System.out.println("After Swap the ArrayList");
        System.out.println(ArrList);
    }
}
```

**Output**

```java
Before Swap the ArrayList 
[Item 1, Item 2, Item 3, Item 4, Item 5]
After Swap the ArrayList
[Item 1, Item 3, Item 2, Item 4, Item 5]
```

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to swap two elements in an ArrayList

import java.util.ArrayList;
import java.util.Collections;

public class GFG {

    public static void main(String a[]) throws Exception
    {

        // Create the Array List
        ArrayList<String> ArrList = new ArrayList<String>();

        // add the values in Array List
        ArrList.add("Item 1");
        ArrList.add("Item 2");
        ArrList.add("Item 3");
        ArrList.add("Item 4");
        ArrList.add("Item 5");

        // display Array List before swap
        System.out.println("Before Swap the ArrayList ");
        System.out.println(ArrList);

        // Swapping the elements at -1 and 2 indices
        // Throws IndexOutOfBounds Exception
        Collections.swap(ArrList, -1, 2);
    }
}
```

**输出**

```java
Exception in thread "main" java.lang.IndexOutOfBoundsException: Index -1 out of bounds for length 5
    at java.base/jdk.internal.util.Preconditions.outOfBounds(Preconditions.java:64)
    at java.base/jdk.internal.util.Preconditions.outOfBoundsCheckIndex(Preconditions.java:70)
    at java.base/jdk.internal.util.Preconditions.checkIndex(Preconditions.java:248)
    at java.base/java.util.Objects.checkIndex(Objects.java:372)
    at java.base/java.util.ArrayList.get(ArrayList.java:458)
    at java.base/java.util.Collections.swap(Collections.java:501)
    at GFG.main(GFG.java:27)
```