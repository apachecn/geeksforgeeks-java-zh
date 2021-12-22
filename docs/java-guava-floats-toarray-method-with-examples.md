# Java 番石榴| Floats.toArray()方法，带示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-to array-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-toarray-method-with-examples/)

番石榴库中 **[Floats 类](https://www.geeksforgeeks.org/floats-class-guava-java/)** 的 **toArray()** 方法用于将作为参数传递给该方法的浮点值转换为浮点数组。这些浮点值作为集合传递给此方法。此方法返回一个浮点数组。

**语法:**

> 公静浮[] toArray(集合<？延伸号>集合)

**参数:**该方法接受一个强制参数*集合*，该集合是要转换为浮点数组的浮点值的集合。

**返回值:**这个方法以相同的顺序返回一个包含与集合相同值的浮点数组。

**异常:**如果传递的集合或其任何元素为空，该方法将抛出 ***空指针异常*** 。

下面的程序说明了 toArray()方法的使用:

**例 1 :**

```java
// Java code to show implementation of
// Guava's Floats.toArray() method

import com.google.common.primitives.Floats;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a List of Floats
        List<Float> myList
            = Arrays.asList(1.2f, 2.3f, 3.4f, 4.5f, 5.6f);

        // Using Floats.toArray() method to convert
        // a List or Set of Float to an array of Float
        float[] arr = Floats.toArray(myList);

        // Displaying an array containing each
        // value of collection,
        // converted to a float value
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出:**

```java
[1.2, 2.3, 3.4, 4.5, 5.6]

```

**例 2 :**

```java
// Java code to show implementation of
// Guava's Floats.toArray() method

import com.google.common.primitives.Floats;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {
            // Creating a List of Floats
            List<Float> myList
                = Arrays.asList(1.2f, 2.3f, 3.4f, null);

            // Using Floats.toArray() method
            // to convert a List or Set of Float
            // to an array of Float.
            // This should raise "NullPointerException"
            // as the collection contains "null"
            // as an element
            float[] arr = Floats.toArray(myList);

            // Displaying an array containing each
            // value of collection,
            // converted to a float value
            System.out.println(Arrays
                                   .toString(arr));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.NullPointerException

```

**参考:**[https://Google . github . io/guava/releases/19.0/API/docs/com/Google/common/primitive/floats . html # to array(Java . util . collection)](https://google.github.io/guava/releases/19.0/api/docs/com/google/common/primitives/Floats.html#toArray(java.util.Collection))