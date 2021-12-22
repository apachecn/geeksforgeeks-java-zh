# 打印数组元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序打印数组元素/](https://www.geeksforgeeks.org/java-program-to-print-the-elements-of-an-array/)

将在 java 中创建一个数组，元素将存储在其中。成功插入后，阵列中的所有元素都会打印出来。

[数组](https://www.geeksforgeeks.org/arrays-in-java/)用于在单个变量中存储多个值，而不是为每个值声明单独的变量。用户只需参考插入的第一个元素的索引号就可以访问这些元素。这是因为这个数据结构的 ttraits 由一组类似类型的变量按顺序存储在内存中，这些变量通过引用索引号由一个共同的名称元素引用。在 java 中，数组的工作方式与在 C/C++中不同。

![](img/8cb539709f616ce76d2904a850a3c608.png)

*   **在 Java 中，所有数组都是动态分配的**。
*   由于数组是 Java 中的对象，用户可以使用对象属性 *length* 找到它们的长度。这与使用函数 *sizeof()* 计算长度的 C/C++不同
*   Java 数组变量也可以像其他变量一样，在数据类型后用[]声明。
*   数组中的变量是有序的，每个变量都有一个从 0 开始的索引。
*   Java 数组也可以用作静态字段、局部变量或方法参数。
*   数组的大小必须由 int 值指定，不能是长的或短的。
*   数组类型的直接超类是[对象](https://www.geeksforgeeks.org/object-class-in-java/)。
*   每个数组类型都实现了接口[可克隆](https://www.geeksforgeeks.org/marker-interface-java/)和 [java.io.Serializable](https://www.geeksforgeeks.org/serialization-in-java/) 。

**示例:**

```
array_mame = {2 , 7 , 4 , 1 , 4}
Output: 2 7 4 1 4

array_name = {2 , 7, -1 , 6 , -3}
Output: 2 7 -1 6 -3

```

**接近:**

*   **使用循环**
*   **使用标准库阵列**

**方法 1:使用循环打印数组元素**

***算法:***

1.  声明并初始化数组
2.  通过递增迭代变量的值在数组中循环
3.  打印出数组的每个元素

实施:

下面是一个 java 例子，演示了数组的打印元素

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Print the Elements of an Array
// Using loops (considering for loop here)
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Initialize array of random numbers and size
        // Suppose array named 'arr' contains 9 elements
        int[] arr = { -7, -5, 5, 10, 0, 3, 20, 25, 12 };

        System.out.print("Elements of given array are: ");

        // Looping through array by incrementing value of i
        //'i' is an index of array 'arr'
        for (int i = 0; i < arr.length; i++) {

            // Print array element present at index i
            System.out.print(arr[i] + " ");
        }
    }
}
```

**输出:**

```
Elements of given array are: -7 -5 5 10 0 3 20 25 12 

```

**时间复杂度:O(n)** 这里除了变量占用的单元内存之外，没有其他主要的执行发生，甚至在作用域结束时被破坏。只要使用一个循环就有迭代，所用时间总是 n 的数量级。如果嵌套，则嵌套的循环数的顺序

**空间复杂度:O(n)** 无论使用什么循环，考虑到整个数组被填满的最坏情况，所以它只占用数组在内存中占用的空间。

**方法 2:** **使用标准库数组**打印数组元素

***算法:***

1.  声明并初始化数组
2.  使用打印语句内的[*arrays . tostring()*](https://www.geeksforgeeks.org/arrays-tostring-in-java-with-examples/)功能打印数组

实施:

使用标准库数组打印数组元素的 Java 程序:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Print the Elements of an Array

// Importing specific array class
// so as to use inbuilt functions
import java.util.Arrays;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Initialize array
        // Array 'arr' contains 9 elements
        int[] arr = { -7, -5, 5, 10, 0, 3, 20, 25, 12 };

        System.out.print("Elements of given array are: ");

        // Pass the array 'arr' in Arrays.toString()
        // function to print array
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出:**

```
Elements of given array are: [-7, -5, 5, 10, 0, 3, 20, 25, 12]

```

**时间复杂度** : **O(n)**

**空间复杂度:O(n)**