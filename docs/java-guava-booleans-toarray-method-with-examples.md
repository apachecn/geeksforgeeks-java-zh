# Java 番石榴| Booleans.toArray()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-booleans-to array-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-toarray-method-with-examples/)

番石榴库中 **[布尔类](https://www.geeksforgeeks.org/booleans-class-guava-java/)** 的 **toArray()** 方法用于将作为参数传递给该方法的布尔值转换为布尔数组。这些布尔值作为集合传递给此方法。此方法返回一个布尔数组。

**语法:**

> 公共静态布尔[] toArray(集合<布尔>集合)

**参数:**该方法接受一个强制参数*集合*，该集合是要转换为布尔数组的布尔值的集合。

**返回值:**该方法返回一个布尔数组，该数组包含与集合相同的值，顺序相同。

**异常:**如果传递的集合或其任何元素为空，该方法将抛出 ***空指针异常*** 。

下面的程序说明了 toArray()方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Booleans.toArray() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a List of Boolean
        List<Boolean> myList
            = Arrays.asList(false, true,
                            false, false);

        // Using Booleans.toArray() method to convert
        // a List or Set of Boolean to an array
        // of Boolean
        boolean[] arr = Booleans.toArray(myList);

        // Displaying an array containing each
        // value of collection,
        // converted to a boolean value
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出:**

```
[false, true, false, false]

```

**例 2:**

```
// Java code to show implementation of
// Guava's Booleans.toArray() method

import com.google.common.primitives.Booleans;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {
        // Creating a List of Boolean
        List<Boolean> myList
            = Arrays.asList(true, true, false);

        // Using Booleans.toArray() method to convert
        // a List or Set of Boolean to an array
        // of Boolean
        boolean[] arr = Booleans.toArray(myList);

        // Displaying an array containing each
        // value of collection,
        // converted to a boolean value
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出:**

```
[true, true, false]

```

**参考:**[https://Google . github . io/guava/releases/20.0/API/docs/com/Google/common/primitive/booleans . html # to array-Java . util . collection-](https://google.github.io/guava/releases/20.0/api/docs/com/google/common/primitives/Booleans.html#toArray-java.util.Collection-)