# Java 番石榴|短裤.包含()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-shots-contains-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-contains-method-with-examples/)

**短裤. contains()** 是番石榴库中[短裤类](https://www.geeksforgeeks.org/shorts-class-guava-java/)的一种方法，用于检查值**目标**是否作为数组中的元素出现。这些目标值和数组都作为该方法的参数。它返回一个布尔值，说明目标值是否存在。

**语法:**

```java
public static boolean contains(short[] array,
                               short target)

```

**参数:**该方法取两个强制参数:

*   **Array:** is an array of short values to search for. It may also be empty.
*   **Target:** is the original short value to be searched in the array.

**返回值:**该方法返回一个布尔值，说明数组中是否存在目标值。如果目标存在，则返回*真*。

下面的程序说明了上述方法的使用:

**示例-1 :**

```java
// Java code to show implementation of
// Guava's Shorts.contains() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = { 5, 4, 3, 2, 1 };

        short target = 3;

        // Using Shorts.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Shorts.contains(arr, target))
            System.out.println("Target is present in the array");
        else
            System.out.println("Target is not present in the array");
    }
}
```

**输出:**

```java
Target is present in the array

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Shorts.contains() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating a short array
        short[] arr = { 2, 4, 6, 8, 10 };

        short target = 7;

        // Using Shorts.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Shorts.contains(arr, target))
            System.out.println("Target is present in the array");
        else
            System.out.println("Target is not present in the array");
    }
}
```

**输出:**

```java
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/primitives/短裤. html # contains-short:A-short-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#contains-short:A-short-)