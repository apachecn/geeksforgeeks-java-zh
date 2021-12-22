# 比较两个浮点数组的 Java 程序

> 原文:[https://www . geeksforgeeks . org/Java-比较两个浮点数组的程序/](https://www.geeksforgeeks.org/java-program-to-compare-two-float-arrays/)

一个[](https://www.geeksforgeeks.org/introduction-to-arrays/)**数组是存储在连续存储位置的项目的集合。想法是将多个相同类型的项目存储在一起。基础值是索引 0，两个索引之间的差异是偏移量。**

**在这个程序中，我们需要比较两个具有**浮点**类型元素的数组。**

> ****如果两个数组以相同的顺序包含相同的元素，则它们是相等的。如果两个数组引用都为空，则认为两个数组引用相等。****

****示例:****

```java
float[] floatV1 = new float[] { 3.1f, 7.5f, 8.3f };
float[] floatV2 = new float[] { 8.3f, 8.8f, 9.2f };
float[] floatV3 = new float[] { 3.1f, 7.5f, 8.3f };
float[] floatV4 = new float[] { 3.2f, 5.5f, 5.3f };

if we compare the two arrays using Arrays.equals() method, it will return true/false.

Arrays.equals(floatV1, floatV2) will give us false
Arrays.equals(floatV3, floatV4) will give us false
Arrays.equals(floatV1, floatV3) will give us true
```

****有两种方法可以比较两个浮点数组:****

1.  **只需遍历整个数组并逐一比较每个元素。**
2.  **使用 Arrays.equals(arr1，arr2)方法**

****方法 1:** 通过简单地迭代整个数组，并逐一比较每个元素。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to compare two float arrays
// using simple iteration

import java.util.Arrays;
public class GFG {
    public static void main(String args[])
    {
        // declaring values in float arrays
        float[] floatV1 = new float[] { 3.1f, 7.5f, 8.3f };
        float[] floatV2 = new float[] { 8.9f, 8.8f, 9.2f };
        float[] floatV3 = new float[] { 3.1f, 7.5f, 8.3f };

        System.out.println(compareArrays(floatV2, floatV3));
        System.out.println(compareArrays(floatV1, floatV3));
        System.out.println(compareArrays(floatV1, floatV2));
    }
    public static boolean compareArrays(float arr1[],float arr2[])
    {
        // if the length of the two arrays are not
        // same then the arrays cannot be equal
        if (arr1.length != arr2.length)
            return false;

        for (int i = 0; i < arr1.length; i++) {

            // if the two ith elements of the two arrays
            // are not same then simply return false
            // and do not check further elements
            if (arr1[i] != arr2[i])
                return false;
        }

        // else if we come out of the for loop
        // successfully without returning false ,
        // then that means all the elements were equal
        return true;
    }
}
```

****Output**

```java
false
true
false
```** 

****方法二:使用**[**array . equals()**](https://www.geeksforgeeks.org/java-util-arrays-equals-java-examples/)**方法****

****语法:****

```java
public static boolean equals(int[] a, int[] a2)
```

****参数:****

*   **a–测试一个数组的相等性**
*   **a2–要测试相等性的另一个阵列**

****如果两个数组相等，则返回:** true**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to compare two float arrays
// using Arrays.equals() method

import java.util.Arrays;
public class GFG {
    public static void main(String args[])
    {
        // declaring values in float arrays
        float[] floatV1 = new float[] { 3.1f, 7.5f, 8.3f };
        float[] floatV2 = new float[] { 8.9f, 8.8f, 9.2f };
        float[] floatV3 = new float[] { 3.1f, 7.5f, 8.3f };
        float[] floatV4 = new float[] { 3.4f, 5.5f, 5.3f };

        // printing and comparing the arrays
        // as it will return boolean value
        // i.e. either true or false
        System.out.println(Arrays.equals(floatV1, floatV2));
        System.out.println(Arrays.equals(floatV2, floatV3));
        System.out.println(Arrays.equals(floatV3, floatV4));
        System.out.println(Arrays.equals(floatV1, floatV3));
        System.out.println(Arrays.equals(floatV1, floatV4));
    }
}
```

****Output**

```java
false
false
false
true
false
```**