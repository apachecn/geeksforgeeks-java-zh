# Java 中的双流顺序()

> 原文:[https://www.geeksforgeeks.org/doublestream-sequential-java/](https://www.geeksforgeeks.org/doublestream-sequential-java/)

**双流顺序()**返回顺序双流。它可能会自己返回，要么是因为流已经是顺序的，要么是因为基础流状态被修改为顺序的。

双流顺序()是一个 ***中间操作*** 。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```
DoubleStream sequential()

Where, DoubleStream is a sequence of primitive
double-valued element.

```

**返回值:**一个连续的双流。
**示例 1 :** 双流顺序()返回顺序双流。

```
// Java code for DoubleStream sequential()
// to return a sequential DoubleStream.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(3.3, 5.4, 9.2,
                                              12.1, 14.4);

        // Using DoubleStream sequential()
        DoubleStream streamNew = stream.sequential();

        // Displaying sequential DoubleStream
        streamNew.forEach(System.out::println);
    }
}
```

**Output:**

```
3.3
5.4
9.2
12.1
14.4

```

**示例 2 :** 空双流上的双流顺序()。

```
// Java code for DoubleStream sequential()
// on empty DoubleStream
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an empty DoubleStream
        DoubleStream stream = DoubleStream.empty();

        // To check if it is parallel or not
        System.out.println("parallel : " + stream.isParallel());

        stream = stream.parallel();

        // To check if it is parallel or not
        System.out.println("parallel : " + stream.isParallel());

        stream = stream.sequential();

        // To check if it is parallel or not
        System.out.println("parallel : " + stream.isParallel());
    }
}
```

**Output:**

```
parallel : false
parallel : true
parallel : false

```