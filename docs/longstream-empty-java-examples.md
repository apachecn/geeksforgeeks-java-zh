# Java 中的 LongStream 空()带示例

> 原文:[https://www . geesforgeks . org/longstream-empty-Java-examples/](https://www.geeksforgeeks.org/longstream-empty-java-examples/)

**LongStream empty()** 是 java.util.stream.LongStream 中的一个方法，这个方法返回一个空的顺序 LongStream。
**语法:**

```java
static LongStream empty() 

```

**参数:**

1.  **LongStream :** 原始长值元素的序列。

**返回值:**一个空的连续长流。

**示例 1 :** 创建空的长流。

```java
// Java code for LongStream empty()
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

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