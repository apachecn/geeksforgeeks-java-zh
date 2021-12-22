# Java 中的 IntStream builder()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/intstream-builder-Java/

**IntStream builder()** 返回一个 IntStream 的构建器。

**语法:**

```java
static IntStream.Builder builder()

```

**参数:**

1.  **IntStream。构建器:**一个 IntStream 的可变构建器。流构建器有一个生命周期，它从构建阶段开始，在此期间可以添加元素，然后过渡到构建阶段，在此阶段之后可以不添加元素。

**返回值:**该函数返回一个输入流的构建器。

**例 1 :**

```java
// Java code for IntStream builder()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream using
        // IntStream builder()
        IntStream stream = IntStream.builder().add(-1).build();

        // Displaying the elements
        stream.forEach(System.out::println);
    }
}
```

输出:

```java
-1

```

**例 2 :**

```java
// Java code for IntStream builder()
import java.util.*;
import java.util.stream.Stream;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream using
        // IntStream builder()
        IntStream stream = IntStream.builder()
                              .add(-1).add(0).add(2).add(4).add(7).build();

        // Displaying the elements
        stream.forEach(System.out::println);
    }
}
```

输出:

```java
-1
0
2
4
7

```