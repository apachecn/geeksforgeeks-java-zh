# Java 中的 LongStream builder()

> 原文:[https://www.geeksforgeeks.org/longstream-builder-java/](https://www.geeksforgeeks.org/longstream-builder-java/)

**LongStream builder()** 返回一个 LongStream 的构建器。

**语法:**

```
static LongStream.Builder builder()

```

**参数:**

1.  **LongStream。构建器:**一个长流的可变构建器。流构建器有一个生命周期，它从构建阶段开始，在此期间可以添加元素，然后过渡到构建阶段，在此阶段之后可以不添加元素。

**返回值:**函数返回一个 LongStream 的构建器。

**例 1 :**

```
// Java code for LongStream builder()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream using
        // LongStream builder()
        LongStream stream = LongStream.builder().add(0).build();

        // Displaying the elements
        stream.forEach(System.out::println);
    }
}
```

输出:

```
0

```

**例 2 :**

```
// Java code for LongStream builder()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a LongStream using
        // LongStream builder()
        LongStream stream = LongStream.builder().add(1L).add(3L).add(5L).add(7L).add(9L).build();

        // Displaying the elements
        stream.forEach(System.out::println);
    }
}
```

输出:

```
1
3
5
7
9

```