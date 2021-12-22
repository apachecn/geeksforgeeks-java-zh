# Java 中的 LongStream 顺序()

> 原文:[https://www.geeksforgeeks.org/longstream-sequential-java/](https://www.geeksforgeeks.org/longstream-sequential-java/)

**长流顺序()**返回一个连续的长流。它可能会自己返回，要么是因为流已经是顺序的，要么是因为基础流状态被修改为顺序的。LongStream 顺序()是一个 ***中间操作*** 。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```
LongStream sequential()

Where, LongStream is a sequence of primitive
long-valued element.

```

**例 1 :**

```
// Java code for LongStream sequential()
// to return a sequential LongStream.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(3L, 5L, 9L, 12L, 14L);

        // Using LongStream sequential()
        LongStream streamNew = stream.sequential();

        // Displaying sequential LongStream
        streamNew.forEach(System.out::println);
    }
}
```

**Output:**

```
3
5
9
12
14

```

**例 2 :**

```
// Java code for LongStream sequential()
// to return a sequential LongStream.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream of elements
        // in range [-2, 4)
        LongStream stream = LongStream.range(-2L, 4L);

        // Using LongStream sequential()
        LongStream streamNew = stream.sequential();

        // Displaying sequential IntStream
        streamNew.forEach(System.out::println);
    }
}
```

**Output:**

```
-2
-1
0
1
2
3

```