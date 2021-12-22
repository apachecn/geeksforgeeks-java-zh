# 爪哇番石榴| Doubles.min()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-min-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-min-method-with-examples/)

**双打. min()** 是[番石榴库](https://www.geeksforgeeks.org/guava-library-java/)中[双打类](https://www.geeksforgeeks.org/doubles-class-guava-java/)的一种方法，用于查找数组中最少出现的**值。此方法返回的值是指定数组中最小的双精度值。**

****语法:****

```
public static double min(double... array) 
```

****参数:**该方法取一个强制参数 ***数组*** ，该数组是非空的*双*值数组。**

****返回值:**该方法返回一个双精度值，该值是指定数组中的最小值。**

****异常:**阵为空则法掷***IllegalArgumentException***。**

**下面的程序说明了上述方法的使用:**

****例 1 :****

```
// Java code to show implementation of
// Guava's Doubles.min() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a Double array
        double[] arr = { 2.2, 4.3, 6.4, 10.5,
                         0.6, -5.7, 15.8 };

        // Using Doubles.min() method to get the
        // minimum value present in the array
        System.out.println("Minimum Value is : "
                           + Doubles.min(arr));
    }
}
```

****输出:**

```
Minimum Value is : -5.7

```

**例 2 :**

```
// Java code to show implementation of
// Guava's Doubles.min() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a Double array
        double[] arr = {};

        try {
            // Using Doubles.min() method to get the
            // minimum value present in the array
            // This should raise "IllegalArgumentException"
            // as the array is empty
            System.out.println("Minimum Value is : "
                               + Doubles.min(arr));
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

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/double . html # min(double…)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#min(double...))**