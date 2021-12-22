# Java 中的 IntStream parallel()

> 原文:[https://www.geeksforgeeks.org/intstream-parallel-java/](https://www.geeksforgeeks.org/intstream-parallel-java/)

**IntStream parallel()** 是 java.util.stream.IntStream 中的一个方法，这个方法返回一个并行的 IntStream，也就是说它可能会自己返回，要么是因为流已经存在，要么是因为底层流状态被修改为并行。

IntStream parallel()是一个**中间操作**。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```
IntStream parallel()

Where, IntStream is a sequence of 
primitive int-valued elements and the function 
returns a parallel IntStream.

```

下面给出了一些例子来更好地理解这个函数。
**例 1 :**

```
// Java program to demonstrate working of
// IntStream parallel() on a given range
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a stream of integers
        IntStream stream = IntStream.range(5, 12);

        System.out.println("The corresponding " + 
                         "parallel IntStream is :");
        stream.parallel().forEach(System.out::println);
    }
}
```

输出:

```
The corresponding parallel IntStream is :
9
8
11
10
6
5
7

```

**例 2 :**

```
// Printing sequential stream for the 
// same input as above example 1.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        IntStream stream = IntStream.range(5, 12);

        System.out.println("The corresponding " + 
                      "sequential IntStream is :");
        stream.sequential().forEach(System.out::println);
    }
}
```

输出:

```
The corresponding sequential IntStream is :
5
6
7
8
9
10
11

```

**例 3 :**

```
// Java program to show sorted output
// of parallel stream.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating a stream of integers
        IntStream stream = IntStream.of(3, 4, 1, 5, 2, 3, 9);

        System.out.println("The sorted parallel" + 
                              " IntStream is :");
        stream.parallel().sorted().forEach(System.out::println);
    }
}
```

输出:

```
The sorted parallel IntStream is :
4
2
3
1
3
5
9

```

请注意，它仍然显示为未排序。那是因为 forEach()正在被使用。要按排序顺序处理项目，请使用 forEachOrdered()。但是请注意，这否定了使用并行的优势。