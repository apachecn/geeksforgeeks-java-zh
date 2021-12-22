# 如何在 Java 中填充(一次初始化)一个数组？

> 原文:[https://www . geesforgeks . org/如何在 java 中填充初始化一次数组/](https://www.geeksforgeeks.org/how-to-fill-initialize-at-once-an-array-in-java/)

一个[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)是一组相似类型的变量，它们被一个共同的名字所引用。数组可以包含原语(int、char 等)。)以及类的对象(或非基元)引用，具体取决于数组的定义。在原始数据类型的情况下，实际值存储在连续的内存位置。对于类的对象，实际的对象存储在堆段中。Java 中有六种填充数组的方法。它们如下:

1.  Use for loop to fill values
2.  Declare them at creation time.
3.  使用 [Arrays.fill()](https://www.geeksforgeeks.org/arrays-fill-java-examples/)
4.  使用[阵列。()副本](https://www.geeksforgeeks.org/arrays-copyof-in-java-with-examples/)
5.  、setall()数组
6.  僧曰[阵列有用。翻制()](https://www.geeksforgeeks.org/arraylist-clone-method-in-java-with-examples/)

### 方法 1:使用 for 循环填充值

在这个方法中，我们通过循环运行空数组，并将值放在每个位置。这主要用于编程，因为它有助于编码器在每个位置放置所需的值。

#### <u>例</u>:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to fill the element in an array
import java.util.*;

public class Gfg {

    // Main function
    public static void main(String args[]) throws Exception 
    {

        // Array Declaration
        int array[] = new int[10];

        // Adding elements in the array
        for (int i = 0; i < array.length; i++) 
        {
            array[i] = i + 1;
        }

        // Printing the elements
        for (int i = 0; i < array.length; i++) 
        {
            System.out.print(array[i] + " ");
        }
   }
}
```

#### **输出:**

```
1 2 3 4 5 6 7 8 9 10

```

### 方法 2:在创建时声明它们

在这个方法中，我们在创建时声明数组的元素。

#### <u>例</u>:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to fill the element in an array
import java.util.*;

public class GFG
{

    // Main function
    public static void main(String args[]) throws Exception 
    {

        // Array Declaration with elements
        int array[] = { 1, 2, 3, 4, 5 };

        // Printing the elements
        for (int i = 0; i < array.length; i++)
        {
            // Printing Elements
            System.out.print(array[i] + " ");
        }
   }
}
```

#### **输出:**

```
1 2 3 4 5

```

### 方法 3:使用数组。填充()

java.util.Arrays.fill()方法在 java.util.Arrays 类中。此方法将指定的数据类型值分配给指定数组的指定范围的每个元素。你可以从这篇 [**文章**](https://www.geeksforgeeks.org/arrays-fill-java-examples/) 中了解更多。

#### <u>例</u>:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to fill the element in an array
import java.util.*;

public class Gfg {

    // Main function
    public static void main(String args[]) throws Exception {

        // Empty Array Declaration
        int array[] = new int[10];

        // Filling the data
        Arrays.fill(array, 10);

        // Printing the data
        System.out.println("Array completely filled with 10\n" 
                            + Arrays.toString(array));
   }
}
```

#### **输出:**

```
Array completely filled with 10
[10, 10, 10, 10, 10, 10, 10, 10, 10, 10]

```

### 方法 4:使用数组

方法在 java.util.Arrays 类中。它复制指定的数组，用 false 截断或填充(如有必要)，使副本具有指定的长度。你可以从这篇 [**文章**](https://www.geeksforgeeks.org/arrays-copyof-in-java-with-examples/) 中了解更多。

#### <u>例</u>:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate copyOf when new array 
// is of higher length. 
import java.util.Arrays; 

public class Gfg { 
public static void main(String args[])
   { 
    // initializing an array original 
    int[] org = new int[] {1, 2 ,3}; 

    System.out.println("Original Array : \n"); 
    for (int i = 0; i < org.length; i++) 
        System.out.print(org[i] + " "); 

    // copying array org to copy 
    // Here, new array has 5 elements - two 
    // elements more than the original array 
    int[] copy = Arrays.copyOf(org, 5); 

    System.out.print("\nNew array copy (of higher length):\n"); 
    for (int i = 0; i < copy.length; i++) 
        System.out.print(copy[i] + " "); 
    } 
}
```

#### **输出:**

```
Original Array:
1 2 3 
New array copy (of higher length):
1 2 3 0 0

```

### 5:使用数组

它通过计算每个元素的函数来设置指定数组中的所有元素。你可以从这篇 [**文章**](https://www.geeksforgeeks.org/java-util-arrays-parallelsetall-arrays-setall-java/) 中了解更多。

#### <u>例</u>:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to illustrate setAll to set value
import java.util.Arrays; 

public class Gfg { 

// Main function
public static void main(String args[]) { 
    // initializing an array
    int[] array = new int[10];

    // Setting the value in the array
    Arrays.setAll(array, p -> p > 9 ? 0 : p);

    // Printing the array
    System.out.println("Array completely filled: \n" 
                            + Arrays.toString(array));
    }
}
```

#### **输出:**

```
Array completely filled: 
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

```

### 方法 6:使用 ArrayUtils.clone()

Java.util.ArrayList.clone()方法用于创建上述数组列表的浅层副本。它只是创建了一个列表的副本。你可以从这篇 [**文章**](https://www.geeksforgeeks.org/arraylist-clone-method-in-java-with-examples/) 中了解更多。

#### <u>例</u>:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate clone() method 

import java.io.*; 
import java.util.ArrayList; 

public class ArrayListDemo { 

    public static void main(String args[]) 
    { 

        // Creating an empty ArrayList 
        ArrayList<String> list 
            = new ArrayList<String>(); 

        // Use add() method 
        // to add elements in the list 
        list.add("Geeks"); 
        list.add("for"); 
        list.add("Geeks"); 
        list.add("10"); 
        list.add("20"); 

        // Displaying the list 
        System.out.println("First ArrayList: "
                        + list); 

        // Creating another linked list and copying 
        ArrayList sec_list = new ArrayList(); 
        sec_list = (ArrayList)list.clone(); 

        // Displaying the other linked list 
        System.out.println("Second ArrayList is: "
                        + sec_list); 
    } 
}
```

#### **输出:**

```
First ArrayList: [Geeks, for, Geeks, 10, 20]
Second ArrayList is: [Geeks, for, Geeks, 10, 20]

```