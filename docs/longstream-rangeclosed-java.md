# Java 中的 LongStream rangeClosed()

> 原文:[https://www.geeksforgeeks.org/longstream-rangeclosed-java/](https://www.geeksforgeeks.org/longstream-rangeclosed-java/)

**LongStream range closed(long start inclusive，long endInclusive)** 返回一个从 startInclusive(包含)到 endInclusive(包含)的 LongStream，增量步长为 1。

**语法:**

```
static LongStream rangeClosed(long startInclusive, long endInclusive)

```

**参数:**

1.  **longstream:** The sequence of original long-value elements.
2.  **开始包含:**包含初始值。
3.  **结束时间:**包含上限。

**返回值:**长元素范围的连续长流。

**例:**

```
// Implementation of LongStream rangeClosed
// (long startInclusive, long endInclusive)
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.rangeClosed(-4L, 3L);

        // Displaying the elements in range
        // including the lower and upper bound
        stream.forEach(System.out::println);
    }
}
```

**输出:**

```
-4
-3
-2
-1
0
1
2
3

```

**注意:**LongStream range closed(long start inclusive，long endInclusive)基本上像 for 循环一样工作。递增值的等价序列可以按如下顺序产生:

```
for (int i = startInclusive; i <= endInclusive ; i++) 
{
 ...
 ...
 ...
}

```