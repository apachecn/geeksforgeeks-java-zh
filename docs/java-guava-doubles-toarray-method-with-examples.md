# 爪哇番石榴| Doubles.toArray()方法示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-to array-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-toarray-method-with-examples/)

番石榴库中 **[双精度类](https://www.geeksforgeeks.org/doubles-class-guava-java/)** 的 **toArray()** 方法用于将作为参数传递给该方法的双精度值转换为双精度数组。这些双精度值作为集合传递给此方法。此方法返回一个双精度数组。

**语法:**

> 公共静态双[] toArray(集合 extends Number>集合)

**参数:**该方法接受一个强制参数*集合*，该集合是要转换为双数组的双数值的集合。

**返回值:**这个方法返回一个双数组，包含与集合相同的值，顺序相同。

**异常:**如果传递的集合或其任何元素为空，该方法将抛出 ***空指针异常*** 。

下面的程序说明了 toArray()方法的使用:

**例 1 :**

```java
// Java code to show implementation of
// Guava's Doubles.toArray() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a List of Doubles
        List<Double> myList
            = Arrays.asList(1.2, 2.3, 3.4, 4.5, 5.6);

        // Using Doubles.toArray() method to convert
        // a List or Set of Double to an array of Double
        double[] arr = Doubles.toArray(myList);

        // Displaying an array containing each
        // value of collection,
        // converted to a double value
        System.out.println(Arrays.toString(arr));
    }
}
```

**Output:**

```java
[1.2, 2.3, 3.4, 4.5, 5.6]

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Doubles.toArray() method

import com.google.common.primitives.Doubles;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {
            // Creating a List of Doubles
            List<Double> myList
                = Arrays.asList(1.2, 2.3, 3.4, null);

            // Using Doubles.toArray() method
            // to convert a List or Set of Double
            // to an array of Double.
            // This should raise "NullPointerException"
            // as the collection contains "null"
            // as an element
            double[] arr = Doubles.toArray(myList);

            // Displaying an array containing each
            // value of collection,
            // converted to a double value
            System.out.println(Arrays
                                   .toString(arr));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**Output:**

```java
java.lang.NullPointerException

```

**参考:**
[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/doubles . html # to array(Java . util . collection)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Doubles.html#toArray(java.util.Collection))