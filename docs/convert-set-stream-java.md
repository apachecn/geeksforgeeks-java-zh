# 在 Java 中将集合转换为流

> 原文:[https://www.geeksforgeeks.org/convert-set-stream-java/](https://www.geeksforgeeks.org/convert-set-stream-java/)

[Set](https://www.geeksforgeeks.org/set-in-java/) 接口扩展[集合](https://www.geeksforgeeks.org/collections-in-java-2/)接口，[集合](https://www.geeksforgeeks.org/collections-in-java-2/)有 [stream()](https://www.geeksforgeeks.org/stream-in-java/) 方法，返回集合的顺序流。

下面给出了一些例子，以便更好地理解实现。

**示例 1 :** 将整数哈希集转换为整数流。

```
// Java code for converting 
// Set to Stream
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating an Integer HashSet
    Set<Integer> set = new HashSet<>();

    // adding elements in set
    set.add(2);
    set.add(4);
    set.add(6);
    set.add(8);
    set.add(10);
    set.add(12);

    // converting Set to Stream
    Stream<Integer> stream = set.stream();

    // displaying elements of Stream using lambda expression
    stream.forEach(elem->System.out.print(elem+" "));

    }
}
```

**示例 2 :** 将字符串哈希集转换为流。

```
// Java code for converting 
// Set to Stream
import java.util.*;
import java.util.stream.Stream;

class GFG {

    // Driver code
    public static void main(String[] args) {

    // Creating an String HashSet
    Set<String> set = new HashSet<>();

    // adding elements in set
    set.add("Geeks");
    set.add("for");
    set.add("GeeksQuiz");
    set.add("GeeksforGeeks");

    // converting Set to Stream
    Stream<String> stream = set.stream();

    // displaying elements of Stream
    stream.forEach(elem -> System.out.print(elem+" "));

    }
}
```

**注意:**在 HashSet 中插入的对象不能保证以相同的顺序插入。根据对象的哈希代码插入对象。

**[将流转换为 Java 中的集合](https://www.geeksforgeeks.org/convert-stream-set-java/)**