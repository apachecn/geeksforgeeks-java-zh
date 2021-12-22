# Java 中的 IntStream rangeClosed()

> 原文:[https://www.geeksforgeeks.org/intstream-rangeclosed-java/](https://www.geeksforgeeks.org/intstream-rangeclosed-java/)

**IntStream range closed(int startInclusive，int endInclusive)** 返回从 startInclusive(包含)到 endInclusive(包含)的 int stream，增量步长为 1。

**语法:**

```
static IntStream rangeClosed(int startInclusive,   int endInclusive)

```

**参数:**

1.  **intstream:** A series of original int value elements.
2.  **开始包含:**包含初始值。
3.  **结束时间:**包含上限。

**返回值:**int 元素范围的连续 IntStream。

**例:**

```
// Implementation of IntStream rangeClosed
// (int startInclusive, int endInclusive)
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.rangeClosed(-4, 3);

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

**注意:**int stream range closed(int startInclusive，int endInclusive)基本上像 for 循环一样工作。递增值的等价序列可以按如下顺序产生:

```
for (int i = startInclusive; i <= endInclusive ; i++) 
{
 ...
 ...
 ...
}

```