# 爪哇番石榴|短裤 min()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-短裤-min-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-min-method-with-examples/)

**短裤 min()** 法番石榴的[短裤类](https://www.geeksforgeeks.org/shorts-class-guava-java/)用来寻找数组中出现的 ***最少的*** 值。此方法返回的值是指定数组中最小的短值。

**语法:**

```
public static short min(short... array)

```

**参数:**该方法取一个强制参数 ***数组*** ，它是非空的短值数组。

**返回值:**该方法返回一个短值，即指定数组中的最小值。

**异常:**阵为空则法掷***IllegalArgumentException***。

以下示例说明了短裤类的 min()方法:

**例 1:**

```
// Java code to show implementation of
// Guava's Shorts.min() method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a short array
        short[] arr = { 2, 4, 6, 10, 0, -5, 15 };

        // Using Shorts.min() method to get the
        // minimum value present in the array
        System.out.println("Minimum Value is: "
                           + Shorts.min(arr));
    }
}
```

**输出:**

```
Minimum Value is: -5

```

**例 2:**

```
// Java code to show implementation of
// Guava's Shorts.min() method

import com.google.common.primitives.Shorts;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a short array
        short[] arr = {};

        try {

            // Using Shorts.min() method to get the
            // minimum value present in the array
            // This should raise "IllegalArgumentException"
            // as the array is empty
            System.out.println("Minimum Value is: "
                               + Shorts.min(arr));
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

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/primitive/短裤. html # min-short……-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#min-short...-)