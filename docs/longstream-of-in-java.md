# Java 中()的 LongStream

> 原文:[https://www.geeksforgeeks.org/longstream-of-in-java/](https://www.geeksforgeeks.org/longstream-of-in-java/)

### **长 t 的长流**

**LongStream of(long t)** 返回包含单个元素的连续 LongStream。
**语法:**

```java
static LongStream of(long t)

```

**参数:**

1.  **LongStream :** 原始长值元素的序列。
2.  **t :** 代表 LongStream 中的单个元素。

**返回值:** LongStream of(long t)返回一个包含**单个**指定元素的连续 LongStream。

**示例:**

```java
// Java code for LongStream of(long t)
// to get a sequential LongStream
// containing a single element.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream having single element only
        LongStream stream = LongStream.of(-7L);

        // Displaying the LongStream having single element
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```java
-7

```

### **长流(长…值)**

**LongStream of(long…values)**返回一个顺序的有序流，其元素是指定的值。
**语法:**

```java
static LongStream of(long... values)

```

**参数:**

1.  **LongStream :** 原始长值元素的序列。
2.  **值:**表示新流的元素。

**返回值:** LongStream of(long… values)返回一个顺序的有序流，其元素是指定的值。

**例 1 :**

```java
// Java code for LongStream of(long... values)
// to get a sequential ordered stream whose
// elements are the specified values.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(-7L, -9L, -11L);

        // Displaying the sequential ordered stream
        stream.forEach(System.out::println);
    }
}
```

**Output:**

```java
-7
-9
-11

```

**例 2 :**

```java
// Java code for LongStream of(long... values)
// to get a sequential ordered stream whose
// elements are the specified values.
import java.util.*;
import java.util.stream.LongStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an LongStream
        LongStream stream = LongStream.of(-7L, -9L, -11L);

        // Storing the count of elements in LongStream
        long total = stream.count();

        // Displaying the count of elements
        System.out.println(total);
    }
}
```

**Output:**

```java
3

```