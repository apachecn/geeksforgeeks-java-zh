# Java 中的双流构建器()，示例

> 原文:[https://www . geesforgeks . org/double stream-builder-Java-examples/](https://www.geeksforgeeks.org/doublestream-builder-java-examples/)

**双流构建器()**返回双流的构建器。

**语法:**

```
static DoubleStream.Builder builder()

```

**参数:**

1.  **双流。构建器:**双流的可变构建器。流构建器有一个生命周期，它从构建阶段开始，在此期间可以添加元素，然后过渡到构建阶段，在此阶段之后可以不添加元素。

**返回值:**该函数返回双流的构建器。

**例 1 :**

```
// Java code for DoubleStream builder()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream using
        // DoubleStream builder()
        DoubleStream stream = DoubleStream.builder()
                                  .add(2.3)
                                  .build();

        // Displaying the elements
        stream.forEach(System.out::println);
    }
}
```

输出:

```
2.3

```

**例 2 :**

```
// Java code for DoubleStream builder()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream using
        // DoubleStream builder()
        DoubleStream stream = DoubleStream.builder().
        add(2.3).add(-1.2).add(3.5).add(10.74).build();

        // Displaying the elements
        stream.forEach(System.out::println);
    }
}
```

输出:

```
2.3
-1.2
3.5
10.74

```