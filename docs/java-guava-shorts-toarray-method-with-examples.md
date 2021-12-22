# 爪哇番石榴|短裤. toArray()方法带示例

> 原文:[https://www . geesforgeks . org/Java-guava-shots-to array-method-with-examples/](https://www.geeksforgeeks.org/java-guava-shorts-toarray-method-with-examples/)

番石榴库中 **[短裤类](https://www.geeksforgeeks.org/shorts-class-guava-java/)** 的 **toArray()** 方法用于将作为参数传递给该方法的短值转换为短数组。这些短值作为集合传递给此方法。此方法返回一个短数组。

**语法:**

> 公静短[] toArray(集合<？延伸号>集合)

**参数:**该方法接受一个强制参数*集合*，该集合是要转换为短数组的短值集合。

**返回值:**这个方法返回一个短数组，包含与集合相同的值，顺序相同。

**异常:**如果传递的集合或其任何元素为空，该方法将抛出 ***空指针异常*** 。

下面的程序说明了 toArray()方法的使用:

**例 1:**

```
// Java code to show implementation of
// Guava's Shorts.toArray() method

import com.google.common.primitives.Shorts;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        // Creating a List of Shorts
        List<Short> myList
            = Arrays.asList((short)1, (short)2,
                            (short)3, (short)4, (short)5);

        // Using Shorts.toArray() method to convert
        // a List or Set of Short to an array of Short
        short[] arr = Shorts.toArray(myList);

        // Displaying an array containing each
        // value of collection,
        // converted to a short value
        System.out.println(Arrays.toString(arr));
    }
}
```

**输出:**

```
[1, 2, 3, 4, 5]

```

**例 2:**

```
// Java code to show implementation of
// Guava's Shorts.toArray() method

import com.google.common.primitives.Shorts;
import java.util.Arrays;
import java.util.List;

class GFG {

    // Driver's code
    public static void main(String[] args)
    {

        try {
            // Creating a List of Shorts
            List<Short> myList
                = Arrays.asList((short)2,
                                (short)4, null);

            // Using Shorts.toArray() method
            // to convert a List or Set of Short
            // to an array of Short.
            // This should raise "NullPointerException"
            // as the collection contains "null"
            // as an element
            short[] arr = Shorts.toArray(myList);

            // Displaying an array containing each
            // value of collection,
            // converted to a short value
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

**参考:**[https://Google . github . io/guava/releases/23.0/API/docs/com/Google/common/primitives/短裤. html # to array-Java . util . collection-](https://google.github.io/guava/releases/23.0/api/docs/com/google/common/primitives/Shorts.html#toArray-java.util.Collection-)