# IntStream findFirst()在 Java

中

> 哎哎哎:# t0]https://www . geeksforgeeks . org/intstream-findfirst-Java/

**IntStream findFirst()** 返回一个**optionallint**(一个可能包含也可能不包含非空值的容器对象)，描述该流的 **first** 元素，如果该流为空，则返回一个空的 optionallint

**语法:**

```java
OptionalInt findFirst()

Where, OptionalInt is a container object which
may or may not contain a non-null value 
and the function returns an OptionalInt describing the 
first element of this stream, or an empty OptionalInt
if the stream is empty. 

```

**注意:** findFirst()是一个 ***端子-短路*** 操作的 Stream 界面。此方法返回满足中间操作的任何第一个元素。

**示例 1 :** 整数流上的 findFirst()方法。

```java
// Java code for IntStream findFirst()
// which returns an OptionalInt describing
// first element of the stream, or an
// empty OptionalInt if the stream is empty.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(6, 7, 8, 9);

        // Using IntStream findFirst() to return
        // an OptionalInt describing first element
        // of the stream
        OptionalInt answer = stream.findFirst();

        // if the stream is empty, an empty
        // OptionalInt is returned.
        if (answer.isPresent()) 
            System.out.println(answer.getAsInt());        
        else 
            System.out.println("no value");        
    }
}
```

输出:

```java
6

```

**注意:**如果流没有相遇顺序，那么可以返回任何元素。

**示例 2 :** findFirst()方法返回第一个可被 4 整除的元素。

```java
// Java code for IntStream findFirst()
// which returns an OptionalInt describing
// first element of the stream, or an
// empty OptionalInt if the stream is empty.
import java.util.OptionalInt;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // Creating an IntStream
        IntStream stream = IntStream.of(4, 5, 8, 10, 12, 16)
                               .parallel();

        // Using IntStream findFirst().
        // Executing the source code multiple times
        // must return the same result.
        // Every time you will get the same
        // Integer which is divisible by 4.
        stream = stream.filter(num -> num % 4 == 0);

        OptionalInt answer = stream.findFirst();
        if (answer.isPresent()) 
            System.out.println(answer.getAsInt());        
    }
}
```

输出:

```java
4

```