# Java 中的 LongStream toArray()

> 原文:[https://www.geeksforgeeks.org/longstream-toarray-java/](https://www.geeksforgeeks.org/longstream-toarray-java/)

**LongStream toArray()** 返回包含该流元素的数组。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```
long[] toArray()

```

**返回值:**函数返回一个包含该流元素的数组。

**例 1 :**

```
// Java code for LongStream toArray()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.of(1L, 3L, 5L,
                                          Long.MIN_VALUE);

        // Using LongStream toArray()
        long[] arr = stream.toArray();

        // Displaying the elements in array arr
        System.out.println(Arrays.toString(arr));
    }
}
```

输出:

```
[1, 3, 5, -9223372036854775808]

```

**例 2 :**

```
// Java code for LongStream toArray()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream
        LongStream stream = LongStream.range(5L, 12L);

        // Using LongStream toArray()
        long[] arr = stream.toArray();

        // Displaying the elements in array arr
        System.out.println(Arrays.toString(arr));
    }
}
```

输出:

```
[5, 6, 7, 8, 9, 10, 11]

```