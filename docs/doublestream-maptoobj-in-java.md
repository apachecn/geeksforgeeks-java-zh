# Java 中的 double stream map oobjo()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/double stream-map oobj-in-Java/

**DoubleStream mapToObj()** 返回由应用给定函数的结果组成的对象值流。

**语法:**

```java
<U> Stream<U> 
mapToObj(DoubleFunction<? 
extends U> mapper)

```

**参数:**该方法接受以下参数:

1.  **U:** 新流的元素类型。
2.  **[流](https://www.geeksforgeeks.org/stream-in-java/) :** 支持顺序和并行聚合操作的元素序列。
3.  **DoubleFunction :** 表示接受双值参数并产生结果的函数。
4.  **映射器:**应用于每个元素的无状态函数。

**返回值:**该函数返回一个由应用给定函数的结果组成的**对象值流**。

以下示例说明了 mapToObj()方法:

**例 1 :**

```java
// Java code for DoubleStream mapToObj
// (DoubleFunction mapper)

import java.util.*;
import java.util.stream.Stream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream 
        DoubleStream stream = DoubleStream.of(3.4, 4.5, 
                                              6.7, 8.9);

        // Using DoubleStream mapToObj(DoubleFunction mapper)
        // and displaying an object-valued Stream 
        // consisting of the results of 
        // applying the given function
        stream.mapToObj(num ->{return num * num * num ;})
                           .forEach(System.out::println);

    }
}
```

**Output:**

```java
39.303999999999995
91.125
300.76300000000003
704.969

```

**例 2 :**

```java
// Java code for DoubleStream mapToObj
// (DoubleFunction mapper)

import java.util.*;
import java.math.BigDecimal;
import java.util.stream.Stream;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream 
        DoubleStream stream = DoubleStream.of(3.4, 4.5, 
                                              6.7, 8.9);

        // Creating a Stream 
        // Using DoubleStream mapToObj(DoubleFunction mapper)
        Stream<BigDecimal> stream1 = stream
            .mapToObj(BigDecimal::valueOf);

        // Displaying an object-valued Stream 
        // consisting of the results of 
        // applying the given function.
        stream1.forEach(num -> System.out.println
                    (num.add(BigDecimal.TEN)));
    }
}
```

**Output:**

```java
13.4
14.5
16.7
18.9

```

**相关文章:**

*   Java 中的 intstream map oobject()
*   [Java 中的流图()，示例](https://www.geeksforgeeks.org/stream-map-java-examples/)
*   Java 中的长流 map oobject()