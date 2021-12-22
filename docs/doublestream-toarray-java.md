# Java 中的 DoubleStream toArray()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/double stream-toaarray-Java/

**DoubleStream toArray()** 返回包含该流元素的数组。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。执行终端操作后，流管道被认为已消耗，不能再使用。

**语法:**

```
double[] toArray()

```

**返回值:**函数返回一个包含该流元素的数组。

**例:**

```
// Java code for DoubleStream toArray()
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream
        DoubleStream stream = DoubleStream.of(1.2, 3.3,
                                         5.4, 7.1, 9.2);

        // Using DoubleStream toArray()
        double[] arr = stream.toArray();

        // Displaying the elements in array arr
        System.out.println(Arrays.toString(arr));
    }
}
```

输出:

```
[1.2, 3.3, 5.4, 7.1, 9.2]

```