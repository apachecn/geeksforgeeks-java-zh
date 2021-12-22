# Java 中的 IntStream 顺序()

> 原文:[https://www.geeksforgeeks.org/intstream-sequential-java/](https://www.geeksforgeeks.org/intstream-sequential-java/)

**IntStream 顺序()**返回一个顺序的 IntStream。它可能会自己返回，要么是因为流已经是顺序的，要么是因为基础流状态被修改为顺序的。IntStream 顺序()是一个 ***中间操作*** 。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```
IntStream sequential()

Where, IntStream is a sequence of primitive
int-valued element.

```

**例 1 :**

```
// Java code for IntStream sequential()
// to return a sequential IntStream.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(3, 5, 9, 12, 14);

        // Using IntStream sequential()
        IntStream streamNew = stream.sequential();

        // Displaying sequential IntStream
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
// Java code for IntStream sequential()
// to return a sequential IntStream.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream of elements
        // in range [-2, 4)
        IntStream stream = IntStream.range(-2, 4);

        // Using IntStream sequential()
        IntStream streamNew = stream.sequential();

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