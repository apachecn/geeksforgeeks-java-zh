# 爪哇番石榴| Longs.toArray()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-longs-to array-method-with-examples/](https://www.geeksforgeeks.org/java-guava-longs-toarray-method-with-examples/)

番石榴库中 **[Longs 类](https://www.geeksforgeeks.org/longs-class-guava-java/)** 的 **toArray()** 方法用于将作为参数传递给该方法的长值转换为长数组。这些长值作为集合传递给此方法。此方法返回一个长数组。

**语法:**

> 公静长【】toArray(集合<？延伸号>集合)

**参数:**该方法接受一个强制参数*集合*，该集合是要转换为长数组的长值的集合。

**返回值:**该方法返回一个长数组，该数组包含的值与集合中的值相同，顺序相同。

**异常:**如果传递的集合或其任何元素为空，该方法将抛出 ***空指针异常*** 。

下面的程序说明了 toArray()方法的使用:

**例 1 :**

```
// Java code to show implementation of
// Guava's Longs.toArray() method

import com.google.common.primitives.Longs;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a List of Longs
        List<Long> myList
            = Arrays.asList(1L, 2L, 3L, 4L, 5L);

        // Using Longs.toArray() method to convert
        // a List or Set of Long to an array of Long
        long[] arr = Longs.toArray(myList);

        // Displaying an array containing each
        // value of collection,
        // converted to a long value
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出:**

```
[1, 2, 3, 4, 5]

```

**例 2 :**

```
// Java code to show implementation of
// Guava's Longs.toArray() method

import com.google.common.primitives.Longs;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {
            // Creating a List of Longs
            List<Long> myList
                = Arrays.asList(2L, 4L, null);

            // Using Longs.toArray() method
            // to convert a List or Set of Long
            // to an array of Long.
            // This should raise "NullPointerException"
            // as the collection contains "null"
            // as an element
            long[] arr = Longs.toArray(myList);

            // Displaying an array containing each
            // value of collection,
            // converted to a long value
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

```
java.lang.NullPointerException

```

**参考:**[https://Google . github . io/guava/releases/21.0/API/docs/com/Google/common/primitive/longs . html # to array-Java . util . collection-](https://google.github.io/guava/releases/21.0/api/docs/com/google/common/primitives/Longs.html#toArray-java.util.Collection-)