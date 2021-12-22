# IntStream findAny()带示例

> 原文:[https://www.geeksforgeeks.org/intstream-findany-examples/](https://www.geeksforgeeks.org/intstream-findany-examples/)

**IntStream findAny()** 返回一个 **OptionalInt** (一个容器对象，可能包含也可能不包含非空值)来描述流的某个元素，如果流为空，则返回一个空的 OptionalInt。

**语法:**

```
OptionalInt findAny()

Where, OptionalInt is a container object which
may or may not contain a non-null value 
and the function returns an OptionalInt describing some element of
this stream, or an empty OptionalInt if the stream is empty.

```

**注意:** findAny()是一个 ***端子-短路*** 操作的 Stream 界面。此方法返回满足中间操作的任何第一个元素。这是一个短路操作，因为它只需要返回**‘any’**第一个元素，并终止剩余的迭代。

**示例 1 :** 整数流上的 findAny()方法。

```
// Java code for IntStream findAny()
// which returns an OptionalInt describing
// some element of the stream, or an
// empty OptionalInt if the stream is empty.
import java.util.*;
import java.util.stream.IntStream;

class GFG {

    // Driver code
    public static void main(String[] args)
    {
        // Creating an IntStream
        IntStream stream = IntStream.of(6, 7, 8, 9);

        // Using IntStream findAny() to return
        // an OptionalInt describing some element
        // of the stream
        OptionalInt answer = stream.findAny();

        // if the stream is empty, an empty
        // OptionalInt is returned.
        if (answer.isPresent()) {
            System.out.println(answer.getAsInt());
        }
        else {
            System.out.println("no value");
        }
    }
}
```

输出:

```
6

```

**注意:**int stream find any()操作的行为是显式的**非确定性的**，即可以自由选择流中的任意元素。对同一源的多次调用可能不会返回相同的结果。

**示例 2 :** findAny()方法以非确定性方式返回可被 4 整除的元素。

```
// Java code for IntStream findAny()
// which returns an OptionalInt describing
// some element of the stream, or an
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

        // Using IntStream findAny().
        // Executing the source code multiple times
        // may not return the same result.
        // Every time you may get a different
        // Integer which is divisible by 4.
        stream = stream.filter(num -> num % 4 == 0);

        OptionalInt answer = stream.findAny();
        if (answer.isPresent()) {
            System.out.println(answer.getAsInt());
        }
    }
}
```

输出:

```
16

```