# 爪哇番石榴| Longs.concat()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-concat-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-concat-method-with-examples/)

番石榴库中 [Longs 类](https://www.geeksforgeeks.org/longs-class-guava-java/)的 **concat()** 方法用于将多个数组的值连接成一个数组。这些要连接的长数组被指定为此方法的参数。

> **例如:** concat(new long[] {1，2}、new long[] {3，4，5}、new long[] {6，7}
> 返回数组{1，2，3，4，5，6，7}。

**语法:**

```
public static long[] concat(long[]... arrays)

```

**参数:**该方法接受**数组**作为参数，这是该方法要连接的长数组。

**返回值:**这个方法返回一个长数组，这个长数组包含所有指定的长数组值的原始顺序。

下面的程序说明了 concat()方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Longs.concat() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 2 Long arrays
        long[] arr1 = { 1, 2, 3, 4, 5 };
        long[] arr2 = { 6, 2, 7, 0, 8 };

        System.out.println("Long Array 1: "
                           + Arrays.toString(arr1));

        System.out.println("Long Array 2: "
                           + Arrays.toString(arr2));

        // Using Longs.concat() method to combine
        // elements from both arrays
        // into a single array
        long[] res = Longs.concat(arr1, arr2);

        // Displaying the single combined array
        System.out.println("Combined Array: "
                           + Arrays.toString(res));
    }
}
```

**Output:**

```
Long Array 1: [1, 2, 3, 4, 5]
Long Array 2: [6, 2, 7, 0, 8]
Combined Array: [1, 2, 3, 4, 5, 6, 2, 7, 0, 8]

```

**例 2:**

```
// Java code to show implementation of
// Guava's Longs.concat() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 4 long arrays
        long[] arr1 = { 1, 2, 3 };
        long[] arr2 = { 4, 5 };
        long[] arr3 = { 6, 7, 8 };
        long[] arr4 = { 9, 0 };

        System.out.println("Long Array 1: "
                           + Arrays.toString(arr1));

        System.out.println("Long Array 2: "
                           + Arrays.toString(arr2));

        System.out.println("Long Array 3: "
                           + Arrays.toString(arr3));

        System.out.println("Long Array 4: "
                           + Arrays.toString(arr4));

        // Using Longs.concat() method to combine
        // elements from both arrays
        // into a single array
        long[] res
            = Longs
                  .concat(arr1, arr2, arr3, arr4);

        // Displaying the single combined array
        System.out.println("Combined Array: "
                           + Arrays.toString(res));
    }
}
```

**Output:**

```
Long Array 1: [1, 2, 3]
Long Array 2: [4, 5]
Long Array 3: [6, 7, 8]
Long Array 4: [9, 0]
Combined Array: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/primitive/longs . html # concat-long:A……-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#concat-long:A...-)