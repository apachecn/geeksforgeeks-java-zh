# Java 中的 IntStream 迭代器()

> 原文:[https://www.geeksforgeeks.org/intstream-iterator-java/](https://www.geeksforgeeks.org/intstream-iterator-java/)

**IntStream 迭代器()**返回该流元素的迭代器。这是一个 ***终端操作*** ，也就是说，它可能穿越河流产生结果或副作用。

**语法:**

```
PrimitiveIterator.OfInt iterator()

Where, PrimitiveIterator.OfInt is an Iterator 
specialized for int values.

```

**返回值:** IntStream 迭代器()返回该流的元素迭代器。

**例 1 :**

```
// Java code for IntStream iterator()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(2, 4, 6, 8);

        // Using IntStream iterator() to return
        // an iterator for elements of the stream
        PrimitiveIterator.OfInt answer = stream.iterator();

        // Displaying the stream elements
        while (answer.hasNext()) {
            System.out.println(answer.nextInt());
        }
    }
}
```

**Output:**

```
2
4
6
8

```

**例 2 :**

```
// Java code for IntStream iterator()
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream which includes
        // lower bound element but excludes
        // upper bound element
        IntStream stream = IntStream.range(2, 8);

        // Using IntStream iterator() to return
        // an iterator for elements of the stream
        PrimitiveIterator.OfInt answer = stream.iterator();

        // Displaying the stream elements
        while (answer.hasNext()) {
            System.out.println(answer.nextInt());
        }
    }
}
```

**Output:**

```
2
3
4
5
6
7

```