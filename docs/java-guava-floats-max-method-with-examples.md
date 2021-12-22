# 爪哇番石榴| Floats.max()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-max-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-max-method-with-examples/)

**Floats.max()** 是[番石榴库](https://www.geeksforgeeks.org/guava-library-java/)中 [Floats 类](https://www.geeksforgeeks.org/floats-class-guava-java/)的一种方法，用于查找数组中存在的 ***最大*** 值。此方法返回的值是指定数组中最大的浮点值。

**语法:**

```
public static float max(float... array)

```

**参数:**该方法取一个强制参数 ***数组*** ，它是非空的*浮点*值数组。

**返回值:**这个方法返回一个浮点值，它是指定数组中的最大值。

**异常:**阵为空则法掷***IllegalArgumentException***。

下面的程序说明了上述方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Floats.max() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a float array
        float[] arr = { 2.2f, 4.3f, 6.4f, 10.2f,
                        0f, -5.2f, 15.5f, 7.4f };

        // Using Floats.max() method to get the
        // maximum value present in the array
        System.out.println("Maximum value is : "
                           + Floats.max(arr));
    }
}
```

**输出:**

```
Maximum value is : 15.5

```

**例 2 :**

```
// Java code to show implementation of
// Guava's Floats.max() method

import com.google.common.primitives.Floats;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a float array
        float[] arr = {};

        try {
            // Using Floats.max() method to get the
            // maximum value present in the array
            // This should raise "IllegalArgumentException"
            // as the array is empty
            System.out.println("Maximum value is : "
                               + Floats.max(arr));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
java.lang.IllegalArgumentException

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/floats . html # max(float…)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#max(float...))