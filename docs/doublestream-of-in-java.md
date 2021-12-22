# Java 中()的双流

> 原文:[https://www.geeksforgeeks.org/doublestream-of-in-java/](https://www.geeksforgeeks.org/doublestream-of-in-java/)

### **双流(双 t)**

**DoubleStream of(double t)** 返回包含单个元素的顺序 DoubleStream。
**语法:**

```java
static DoubleStream of(double t)

```

**参数:**

1.  **双流:**原始双值元素的序列。
2.  **t :** 代表双流中的单个元素。

**返回值:** DoubleStream of(double t)返回包含**单个**指定元素的连续 DoubleStream。

**示例:**

```java
// Java code for DoubleStream of(double t)
// to get a sequential DoubleStream
// containing a single element.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating a DoubleStream having single
        // element only
        DoubleStream stream = DoubleStream.of(8.2);

        // Displaying the DoubleStream having 
        // single element
        stream.forEach(System.out::println);
    }
}
```

输出:

```java
8.2

```

### **双(双…值)**流

**double stream of(double…values)**返回元素为指定值的顺序有序流。
**语法:**

```java
static DoubleStream of(double... values)

```

**参数:**

1.  **双流:**原始双值元素的序列。
2.  **值:**表示新流的元素。

**返回值:**double stream of(double…values)返回一个顺序的有序流，其元素是指定的值。

**例 1 :**

```java
// Java code for DoubleStream of(double... values)
// to get a sequential ordered stream whose
// elements are the specified values.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(8.2, 5.6, 4.1);

        // Displaying the sequential ordered stream
        stream.forEach(System.out::println);
    }
}
```

输出:

```java
8.2
5.6
4.1

```

**例 2 :**

```java
// Java code for DoubleStream of(double... values)
// to get a sequential ordered stream whose
// elements are the specified values.
import java.util.*;
import java.util.stream.DoubleStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an DoubleStream
        DoubleStream stream = DoubleStream.of(5.2, 4.2, 6.3);

        // Storing the count of elements in DoubleStream
        long total = stream.count();

        // Displaying the count of elements
        System.out.println(total);
    }
}
```

输出:

```java
3

```