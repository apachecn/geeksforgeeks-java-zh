# Java 中的 IntStream empty()带示例

> 原文:[https://www.geeksforgeeks.org/intstream-empty-in-java/](https://www.geeksforgeeks.org/intstream-empty-in-java/)

**IntStream empty()** 是 java.util.stream.IntStream 中的一个方法，这个方法返回一个空的顺序 IntStream。
**语法:**

```java
static <**T**> Stream<**T**> empty()

Where, T is the type of stream elements,
and the function returns an empty sequential stream.

```

**示例 1 :** 创建空的输入流。

```java
// Java code for IntStream empty()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // creating an empty IntStream, a sequence of 
    // primitive int-valued elements
    IntStream stream = IntStream.empty();

    // Displaying an empty sequential stream
    System.out.println(stream.count());
}
}
```

输出:

```java
0

```

**示例 2 :** 创建空 LongStream。

```java
// Java code for LongStream empty() method
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // creating an empty LongStream, a sequence of
    // primitive long-valued elements
    LongStream stream = LongStream.empty();

    // Displaying an empty sequential stream
    System.out.println(stream.count());
}
}
```

输出:

```java
0

```