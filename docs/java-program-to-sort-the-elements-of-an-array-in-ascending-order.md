# 按升序排列数组元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-sort-of-a-array-elements-in-升序/](https://www.geeksforgeeks.org/java-program-to-sort-the-elements-of-an-array-in-ascending-order/)

**问题陈述:**按照升序对给定数组进行排序，使元素从最小到最大排列。下面是一个例子:

假设原始数组如下:

<figure class="table">

| -5 | -9 | eight | Twelve | one | three |

</figure>

对以上数组排序后生成的数组如下 **:**

<figure class="table">

| -9 | -5 | one | three | eight | Twelve |

</figure>

*   元素的排序方式是最小的元素出现在最左边，在本例中是-9。最大的元素将出现在最右边，在这种情况下是 12。

**接近:**

1.  使用冒泡排序(幼稚)
2.  使用数组类的 sort()方法(最优)

**方法 1:** 使用[气泡排序](https://www.geeksforgeeks.org/bubble-sort/)

**算法:**

1.  将相邻元素相互比较。
2.  使用嵌套 for 循环来跟踪。
3.  如果第一个元素大于第二个元素，则交换元素。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to Sort Elements of an Array
// in Ascending Order

// Main class
class GFG {

    // Declaration global variable length
    static int length;

    // Method 1
    // To print the array
    public static void printArray(int[] array)
    {
        // Iterating using for loops
        for (int i = 0; i < length; i++) {
            System.out.print(array[i] + " ");
        }
        System.out.println();
    }

    // Method 2
    // To sort an array
    public static void sortArray(int[] array)
    {
        int temporary = 0;

        // Sort the array 'arr' elements in ascending order
        // using nested for loops
        for (int i = 0; i < length; i++) {
            for (int j = i + 1; j < length; j++) {
                if (array[i] > array[j]) {
                    temporary = array[i];
                    array[i] = array[j];
                    array[j] = temporary;
                }
            }
        }

        // Displaying elements of array after sorting
        System.out.println(
            "Elements of array sorted in ascending order: ");
        printArray(array);
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {
        // Initializing custom array elements
        // The array contains 6 elements.
        int[] array = new int[] { -5, -9, 8, 12, 1, 3 };

        // Initialize length
        length = array.length;

        // Displaying elements of original array
        System.out.print("Elements of original array: ");

        // Call printArray method
        printArray(array);

        // Call sortArray method
        sortArray(array);
    }
}
```

**Output**

```java
Elements of original array: -5 -9 8 12 1 3 
Elements of array sorted in ascending order: 
-9 -5 1 3 8 12 

```

> 时间复杂度:O(n^2)，其中 n 是数组的长度。

**方法 2:** [使用数组类](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/)的 sort()方法

sort()方法是一个 java.util.Arrays 类方法，用于对数组元素进行排序。默认情况下，它按升序对数组元素进行排序。

**语法:**

```java
Arrays.sort(arrayName);
```

**参数:**待排序数组

**返回类型:** NA

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to sort the elements of an array
// in Ascending Order by Inbuilt Methods

// Importing Arrays class from java.util package
import java.util.Arrays;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initialize array
        // The array contains 6 elements.
        int[] array = new int[] { -5, -9, 8, 12, 1, 3 };

        // Displaying elements of original array
        System.out.print("Elements of original array: ");
        for (int i = 0; i < array.length; i++) {
            System.out.print(array[i] + " ");
        }

        // Using Arrays.sort() method to sort array
        // elements in ascending order.
        Arrays.sort(array);

        System.out.println();

        // Displaying elements of array after sorting
        System.out.println(
            "Elements of array sorted in ascending order : "
            + Arrays.toString(array));
    }
}
```

**Output**

```java
Elements of original array: -5 -9 8 12 1 3 
Elements of array sorted in ascending order : [-9, -5, 1, 3, 8, 12]

```

> 时间复杂度:O(n log(n))，其中 n 是数组的大小。