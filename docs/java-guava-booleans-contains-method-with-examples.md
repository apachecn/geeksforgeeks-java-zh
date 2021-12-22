# Java 番石榴| Booleans.contains()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-booleans-contains-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-contains-method-with-examples/)

番石榴库中 **[布尔类](https://www.geeksforgeeks.org/booleans-class-guava-java/)** 的 **contains()** 方法用于检查指定的布尔值数组中是否存在指定的值。要搜索的布尔值和要搜索的布尔数组都被作为参数。

**语法:**

```java
public static boolean contains(boolean[] array,
                               boolean target)

```

**参数:**该方法接受两个强制参数:

*   **Array:** is an array of Boolean values in which to search for the target value.
*   **Target:** is the Boolean value in the array to search for existence.

**返回值:**该方法返回一个布尔值，说明目标布尔值是否存在于指定的布尔数组中。如果数组中存在目标值，则返回*真*。否则返回假。

下面的程序说明了 contains()方法的使用:

**示例-1 :**

```java
// Java code to show implementation of
// Guava's Booleans.contains() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Boolean array
        boolean[] arr = { false, true, false,
                          true, true };

        boolean target = true;

        // Using Booleans.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Booleans.contains(arr, target))
            System.out.println("Target is present "
                               + "in the array");
        else
            System.out.println("Target is not "
                               + "present in the array");
    }
}
```

**输出:**

```java
Target is present in the array

```

**示例–2:**

```java
// Java code to show implementation of
// Guava's Booleans.contains() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Boolean array
        boolean[] arr = { true, true, true,
                          true, true };

        boolean target = false;

        // Using Booleans.contains() method to search
        // for an element in the array. The method
        // returns true if element is found, else
        // returns false
        if (Booleans.contains(arr, target))
            System.out.println("Target is present "
                               + "in the array");
        else
            System.out.println("Target is not present "
                               + "in the array");
    }
}
```

**输出:**

```java
Target is not present in the array

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/primitive/booleans . html # contains-booleans:A-boolean-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#contains-boolean:A-boolean-)