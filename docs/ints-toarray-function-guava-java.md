# Ints toArray()函数|番石榴| Java

> 原文:[https://www . geesforgeks . org/ints-to array-function-guava-Java/](https://www.geeksforgeeks.org/ints-toarray-function-guava-java/)

番石榴的**T1Ints。toArray()** 返回一个包含集合中每个值的数组，以 [Number.intValue()](https://www.geeksforgeeks.org/number-intvalue-method-in-java-with-examples/) 的方式转换为 int 值

**语法:**

```
public static int[] 
    toArray(Collection<? extends Number> collection)

```

**参数:**该方法以*集合*为参数，该参数是*号*实例的集合。

**返回值:**这个方法返回一个数组，包含与集合相同的值，顺序相同，转换为原语。

**异常:**如果集合或其任何元素为空，该方法将抛出 ***空指针异常*** 。

以下示例说明了 Ints.toArray()方法:

**例 1:**

```
// Java code to show implementation of
// Guava's Ints.toArray() method

import com.google.common.primitives.Ints;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a List of Integers
        List<Integer>
            myList = Arrays.asList(1, 2, 3, 4, 5);

        // Using Ints.toArray() method to convert
        // a List or Set of Integer to an array
        // of Int
        int[] arr = Ints.toArray(myList);

        // Displaying an array containing each
        // value of collection,
        // converted to a int value
        System.out.println("Array from given List: "
                           + Arrays.toString(arr));
    }
}
```

**输出:**

```
Array from given List: [1, 2, 3, 4, 5]

```

**示例 2:** 演示 NullPointerException

```
// Java code to show implementation of
// Guava's Ints.toArray() method

import com.google.common.primitives.Ints;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {

            // Creating a List of Integers
            List<Integer>
                myList = Arrays.asList(2, 4, null);

            // Using Ints.toArray() method to convert
            // a List or Set of Integer to an array
            // of Int. This should raise "NullPointerException"
            // as the collection contains "null" as an element
            int[] arr = Ints.toArray(myList);

            // Displaying an array containing each
            // value of collection, converted to a int value
            System.out.println(Arrays.toString(arr));
        }
        catch (Exception e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**输出:**

```
Exception: java.lang.NullPointerException

```

**参考:**[https://Google . github . io/guava/releases/22.0/API/docs/com/Google/common/primitives/ints . html # to array-Java . util . collection-](https://google.github.io/guava/releases/22.0/api/docs/com/google/common/primitives/Ints.html#toArray-java.util.Collection-)