# Java 中的双流并行()

> 原文:[https://www.geeksforgeeks.org/doublestream-parallel-java/](https://www.geeksforgeeks.org/doublestream-parallel-java/)

**DoubleStream parallel()** 是 java.util.stream.DoubleStream 中的一个方法，这个方法返回一个并行的 DoubleStream，也就是说，它可能会自己返回，要么是因为流已经存在，要么是因为底层流状态被修改为并行。

双流并行()是一个**中间操作**。这些操作总是偷懒。中间操作在流实例上被调用，在它们完成处理后，它们给出一个流实例作为输出。

**语法:**

```
DoubleStream parallel()

Where, DoubleStream is a sequence of primitive 
double-valued elements and the function 
returns a parallel DoubleStream.

```

**例 1 :**

```
// Java program to demonstrate working of
// DoubleStream parallel() on a given range
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a stream of doubles
        DoubleStream stream = 
              DoubleStream.of(5.2, 12.6, 4.5, 7.8);

        System.out.println("The corresponding "
                           + "parallel DoubleStream is :");
        stream.parallel().forEach(System.out::println);
    }
}
```

输出:

```
The corresponding parallel DoubleStream is :
4.5
7.8
12.6
5.2

```

**例 2 :**

```
// Printing sequential stream for the
// same input as above example 1.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a stream of doubles
        DoubleStream stream = 
                 DoubleStream.of(5.2, 12.6, 4.5, 7.8);

        System.out.println("The corresponding "
                           + "sequential DoubleStream is :");
        stream.sequential().forEach(System.out::println);
    }
}
```

输出:

```
The corresponding sequential DoubleStream is :
5.2
12.6
4.5
7.8

```

**例 3 :**

```
// Java program to show sorted output
// of parallel stream.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a stream of doubles
        DoubleStream stream =
                DoubleStream.of(2.3, 3.0, 4.5, 6.6);

        System.out.println("The sorted parallel"
                           + " DoubleStream is :");
        stream.parallel().sorted().forEach(System.out::println);
    }
}
```

输出:

```
The sorted parallel DoubleStream is :
4.5
6.6
2.3
3.0

```