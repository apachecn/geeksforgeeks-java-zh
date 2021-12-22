# Java 中的 LongStream min()，示例

> 原文:[https://www.geeksforgeeks.org/longstream-min-java-examples/](https://www.geeksforgeeks.org/longstream-min-java-examples/)

Java 8 中的 java.util.stream.LongStream 处理原语 longs。它以一种新的方式帮助解决了求数组中最大值、求数组中最小值、求数组中所有元素的和、求数组中所有值的平均值等问题。 **LongStream min()** 返回一个描述该流的**最小值**元素的可选值，如果该流为空，则返回一个空的可选值。

**语法:**

```
OptionalLong() min()

Where, OptionalLong is a container object which 
may or may not contain a long value.

```

**例 1 :**

```
// Java code for LongStream min()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // creating a stream
        LongStream stream = LongStream.of(-9L, -18L, 54L,
                                          8L, 7L, 14L, 3L);

        // OptionalLong is a container object
        // which may or may not contain a
        // long value.
        OptionalLong obj = stream.min();

        // If a value is present, isPresent() will
        // return true and getAsLong() will
        // return the value
        if (obj.isPresent()) {
            System.out.println(obj.getAsLong());
        }
        else {
            System.out.println("-1");
        }
    }
}
```

输出:

```
-18

```

**例 2 :**

```
// Java code for LongStream min()
// to get the minimum value in range
// excluding the last element
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // To find minimum in given range
        LongStream stream = LongStream.range(50L, 75L);

        // storing the minimum value in variable
        // if it is present, else show -1.
        long minimum = stream.min().orElse(-1);

        // displaying the minimum value
        System.out.println(minimum);
    }
}
```

输出:

```
50

```

**例 3 :**

```
// Java code for LongStream min()
// to get the minimum value in range
// excluding the last element
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // To find minimum in given range
        LongStream stream = LongStream.range(50L, 50L);

        // storing the minimum value in variable
        // if it is present, else show -1.
        long minimum = stream.min().orElse(-1);

        // displaying the minimum value
        System.out.println(minimum);
    }
}
```

输出:

```
-1

```