# Java 番石榴| Booleans.concat()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-booleans-concat-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-concat-method-with-examples/)

番石榴库中 **[布尔类](https://www.geeksforgeeks.org/booleans-class-guava-java/)** 的 **concat()** 方法用于将多个数组的值连接成一个数组。这些要连接的布尔数组被指定为此方法的参数。

> **例如** : concat(new boolean[] {a，b}，new boolean[] {}，new boolean[] {c}返回数组{a，b，c}。

**语法:**

```
public static boolean[] concat(boolean[]... arrays)

```

**参数:**该方法接受**数组**作为参数，该参数是该方法要连接的布尔数组。

**返回值:**该方法返回一个布尔数组，该数组包含所有指定的布尔数组值的原始顺序。

下面的程序说明了 concat()方法的使用:

**示例-1 :**

```
// Java code to show implementation of
// Guava's Booleans.concat() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating 2 Boolean arrays
        boolean[] arr1 = { true, false, true };
        boolean[] arr2 = { false, false, false, true };

        // Using Booleans.concat() method to combine
        // elements from both arrays into a single array
        boolean[] res = Booleans.concat(arr1, arr2);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**输出:**

```
[true, false, true, false, false, false, true]

```

**示例-2 :**

```
// Java code to show implementation of
// Guava's Booleans.concat() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating 4 boolean arrays
        boolean[] arr1 = { true, false, false };
        boolean[] arr2 = { true, true };
        boolean[] arr3 = { false, false, false };
        boolean[] arr4 = { false, true };

        // Using Booleans.concat() method to combine
        // elements from both arrays into a single array
        boolean[] res
            = Booleans.concat(arr1, arr2, arr3, arr4);

        // Displaying the single combined array
        System.out.println(Arrays.toString(res));
    }
}
```

**输出:**

```
[true, false, false, true, true, false, false, false, false, true]

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/primitive/booleans . html # concat-boolean:A……-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#concat-boolean:A...-)