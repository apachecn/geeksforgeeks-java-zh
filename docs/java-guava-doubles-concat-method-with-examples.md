# 爪哇番石榴| Doubles.concat()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-concat-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-concat-method-with-examples/)

番石榴库中[双打类](https://www.geeksforgeeks.org/doubles-class-guava-java/)的 **concat()** 方法用于将多个数组的值连接成一个数组。这些要连接的双数组被指定为此方法的参数。

> **例如:** concat(new double[] {a，b}、new double[] {}、new double[] {c}
> 返回数组{a，b，c}。

**语法:**

```
public static double[] concat(double[]... arrays)

```

**参数:**该方法接受**数组**作为参数，这是该方法要连接的双数组。

**返回值:**该方法返回一个单双数组，该数组包含所有指定的双数组值的原始顺序。

下面的程序说明了 concat()方法的使用:

**实施例 1:**

```
// Java code to show implementation of
// Guava's Doubles.concat() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating 2 Double arrays
        double[] arr1 = { 1.2, 2.3, 3.5, 4.4, 5.1 };
        double[] arr2 = { 6.2, 2.1, 7.2, 0.4, 8.7 };

        // Using Doubles.concat() method to combine
        // elements from both arrays into a single array
        double[] res = Doubles.concat(arr1, arr2);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**Output:**

```
[1.2, 2.3, 3.5, 4.4, 5.1, 6.2, 2.1, 7.2, 0.4, 8.7]

```

**例 2:**

```
// Java code to show implementation of
// Guava's Doubles.concat() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating 4 Double arrays
        double[] arr1 = { 1.2, 2.3, 3.4 };
        double[] arr2 = { 4.5, 5.6 };
        double[] arr3 = { 6.4, 7.6, 8.7 };
        double[] arr4 = { 9.7, 0.8 };

        // Using Doubles.concat() method to combine
        // elements from both arrays into a single array
        double[] res
            = Doubles.concat(arr1, arr2, arr3, arr4);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**Output:**

```
[1.2, 2.3, 3.4, 4.5, 5.6, 6.4, 7.6, 8.7, 9.7, 0.8]

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitives/double . html # concat(double[]……)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#concat(double[]...))