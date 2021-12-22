# 爪哇番石榴| Longs.min()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-min-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-min-method-with-examples/)

**Longs.min()** 是[番石榴库](https://www.geeksforgeeks.org/guava-library-java/)中 [Longs 类](https://www.geeksforgeeks.org/longs-class-guava-java/)的一种方法，用于查找数组中最少出现的**值。此方法返回的值是指定数组中最小的长值。**

****语法:****

```
public static long min(long... array) 
```

****参数:**此方法采用强制参数 ***数组*** ，该数组是非空的*长*值数组。**

****返回值:**此方法返回一个长值，该值是指定数组中的最小值。**

****异常:**阵为空则法掷***IllegalArgumentException***。**

**下面的程序说明了上述方法的使用:**

****例 1 :****

```
// Java code to show implementation of
// Guava's Longs.min() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a long array
        long[] arr = { 2, 4, 6, 10, 0, -5, 15 };

        // Using Longs.min() method to get the
        // minimum value present in the array
        System.out.println("Minimum Value is : "
                           + Longs.min(arr));
    }
}
```

****输出:**

```
Minimum Value is : -5

```

**例 2 :**

```
// Java code to show implementation of
// Guava's Longs.min() method

import com.google.common.primitives.Longs;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a long array
        long[] arr = {};

        try {
            // Using Longs.min() method to get the
            // minimum value present in the array
            // This should raise "IllegalArgumentException"
            // as the array is empty
            System.out.println("Minimum Value is : "
                               + Longs.min(arr));
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

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/primitive/longs . html # min-long……-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#min-long...-)**