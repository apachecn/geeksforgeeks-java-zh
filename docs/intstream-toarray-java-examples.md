# Java 中的 IntStream toArray()，示例

> 原文:[https://www . geesforgeks . org/int stream-to array-Java-examples/](https://www.geeksforgeeks.org/intstream-toarray-java-examples/)

**IntStream toArray()** 返回包含该流元素的数组。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```
int[] toArray()

```

**返回值:**函数返回一个包含该流元素的数组。

**例 1 :**

```
// Java code for IntStream toArray()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(1, 3, 5, 7, 9);

        // Using IntStream toArray()
        int[] arr = stream.toArray();

        // Displaying the elements in array arr
        System.out.println(Arrays.toString(arr));
    }
}
```

输出:

```
[1, 3, 5, 7, 9]

```

**例 2 :**

```
// Java code for IntStream toArray()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.range(-2, 10);

        // Using IntStream toArray()
        int[] arr = stream.toArray();

        // Displaying the elements in array arr
        System.out.println(Arrays.toString(arr));
    }
}
```

输出:

```
[-2, -1, 0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

```