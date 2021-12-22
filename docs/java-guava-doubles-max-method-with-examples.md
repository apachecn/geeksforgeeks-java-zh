# 爪哇番石榴| Doubles.max()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-max-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-max-method-with-examples/)

**双打. max()** 是[番石榴库](https://www.geeksforgeeks.org/guava-library-java/)中[双打类](https://www.geeksforgeeks.org/doubles-class-guava-java/)的一种方法，用于查找数组中最大的**值。此方法返回的值是指定数组中最大的双精度值。**

****语法:****

```
public static double max(double... array) 
```

****参数:**该方法取一个强制参数 ***数组*** ，该数组是非空的*双*值数组。**

****返回值:**该方法返回一个双精度值，该值是指定数组中的最大值。**

****异常:**阵为空则法掷***IllegalArgumentException***。**

**下面的程序说明了上述方法的使用:**

****例 1 :****

```
// Java code to show implementation of
// Guava's Doubles.max() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Double array
        double[] arr = { 2.2, 4.3, 6.4, 10.2,
                         0, -5.2, 15.5, 7.4 };

        // Using Doubles.max() method to get the
        // maximum value present in the array
        System.out.println("Maximum value is : "
                           + Doubles.max(arr));
    }
}
```

****输出:**

```
Maximum value is : 15.5

```

**例 2 :**

```
// Java code to show implementation of
// Guava's Doubles.max() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Double array
        double[] arr = {};

        try {
            // Using Doubles.max() method to get the
            // maximum value present in the array
            // This should raise "IllegalArgumentException"
            // as the array is empty
            System.out.println("Maximum value is : "
                               + Doubles.max(arr));
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

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/double . html # max(double…)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#max(double...))**