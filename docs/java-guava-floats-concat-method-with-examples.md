# Java 番石榴| Floats.concat()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-concat-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-concat-method-with-examples/)

番石榴库中 [Floats 类](https://www.geeksforgeeks.org/floats-class-guava-java/)的 **concat()** 方法用于将多个数组的值连接成一个数组。这些要连接的浮点数组被指定为此方法的参数。

> **例如:** concat(new float[] {a，b}，new float[] {}，new float[] {c}返回数组{a，b，c}。

**语法:**

```java
public static float[] concat(float[]... arrays)

```

**参数:**该方法接受**数组**作为参数，该参数是该方法要连接的浮点数组。

**返回值:**该方法返回一个浮点数组，该数组包含所有指定的浮点数组值的原始顺序。

下面的程序说明了 concat()方法的使用:

**例 1:**

```java
// Java code to show implementation of
// Guava's Floats.concat() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 2 Float arrays
        float[] arr1 = { 1.2f, 2.3f, 3.5f, 4.4f, 5.1f };
        float[] arr2 = { 6.2f, 2.1f, 7.2f, 0.4f, 8.7f };

        // Using Floats.concat() method to combine
        // elements from both arrays into a single array
        float[] res = Floats.concat(arr1, arr2);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**输出:**

```java
[1.2, 2.3, 3.5, 4.4, 5.1, 6.2, 2.1, 7.2, 0.4, 8.7]

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Floats.concat() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 4 Float arrays
        float[] arr1 = { 1.2f, 2.3f, 3.4f };
        float[] arr2 = { 4.5f, 5.6f };
        float[] arr3 = { 6.4f, 7.6f, 8.7f };
        float[] arr4 = { 9.7f, 0.8f };

        // Using Floats.concat() method to combine
        // elements from both arrays into a single array
        float[] res = Floats.concat(arr1, arr2, arr3, arr4);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**输出:**

```java
[1.2, 2.3, 3.4, 4.5, 5.6, 6.4, 7.6, 8.7, 9.7, 0.8]

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/floats . html # concat(float[]……)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#concat(float[]...))