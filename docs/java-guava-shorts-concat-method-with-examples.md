# 爪哇番石榴|短裤. concat()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-短裤-concat-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-concat-method-with-examples/)

**短裤. concat()** 是番石榴库中[短裤类](https://www.geeksforgeeks.org/shorts-class-guava-java/)的一种方法，用于将多个数组的值连接成单个数组。**例如**，concat(new short[] {a，b}、new short[] {}、new short[] {c}返回数组{a，b，c}。

**语法:**

```
public static short[] concat(short[]... arrays)

```

这里， ***阵*** 代表零个或多个短阵。

**返回值:**包含源数组中所有值的单个数组，按顺序排列。

**示例-1:**

```
// Java code to show implementation of
// Guava's Shorts.concat() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating 2 short arrays
        short[] arr1 = { 1, 2, 3, 4, 5 };
        short[] arr2 = { 6, 2, 7, 0, 8 };

        // Using Shorts.concat() method to combine
        // elements from both arrays into a single array
        short[] res = Shorts.concat(arr1, arr2);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**输出:**

```
[1, 2, 3, 4, 5, 6, 2, 7, 0, 8]

```

**示例-2:**

```
// Java code to show implementation of
// Guava's Shorts.concat() method
import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {
    // Driver's code
    public static void main(String[] args)
    {
        // Creating 4 short arrays
        short[] arr1 = { 1, 2, 3 };
        short[] arr2 = { 4, 5 };
        short[] arr3 = { 6, 7, 8 };
        short[] arr4 = { 9, 0 };

        // Using Shorts.concat() method to combine
        // elements from both arrays into a single array
        short[] res = Shorts.concat(arr1, arr2, arr3, arr4);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**输出:**

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 0]

```

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/primitives/短裤. html # concat-short:A……-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#concat-short:A...-)