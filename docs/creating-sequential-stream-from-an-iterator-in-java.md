# 用 Java 从迭代器创建顺序流

> 原文:[https://www . geesforgeks . org/creating-sequential-stream-from-iterator-in-Java/](https://www.geeksforgeeks.org/creating-sequential-stream-from-an-iterator-in-java/)

[](https://www.geeksforgeeks.org/iterators-in-java/)**迭代器，在 Java 中，用在 Collection Framework 中，一个一个的检索元素。**

**Java 中的**流**是来自数组或集合数据源的对象管道。顺序流是指对象在同一处理系统的单个流中流水线化。其他类型的流包括并行流，其中对象在多处理系统上流水线化。**

**因此，经常需要将迭代器用作顺序流。有许多方法可以做到这一点，这些方法是:**

1.  ****使用拆分器** : [拆分器](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)像其他迭代器一样，用于遍历一个源的元素。源可以是集合、输入输出通道或生成器函数。**

****使用的方法:****

| 班级 | 修饰符和类型 | 方法 | 描述 |
| --- | --- | --- | --- |
| 分离器 | 静态<t>分流器</t> | spliteratorUnknownSize(迭代器 extends T>迭代器，int 特性) | 使用给定的迭代器作为元素源创建拆分器，没有初始大小估计。 |
| StreamSupport | 静态<t>流</t> | 流(拆分器<t>拆分器，布尔并行)</t> | 从拆分器创建新的顺序或并行流。 |

****解释**:拆分器在从迭代器创建顺序流时充当中间体。迭代器首先在[拆分器的帮助下被转换成拆分器。在下面找到这个的方法描述。然后，在**流支持.流()**功能的帮助下，拆分器被转换为顺序流。该函数的**第二个参数**取布尔值来判断要生成的流是否是并行的。](https://docs.oracle.com/javase/8/docs/api/java/util/Spliterators.html#spliteratorUnknownSize-java.util.Iterator-int-)**

****程序:****

```java
// Java program to create a Sequential Stream
// from an Iterator

import java.util.*;
import java.util.stream.*;

class GfG {
    // Function to create a sequential Stream
    // from an Iterator
    public static <T> Stream<T> 
                iteratorToSequentialStream(Iterator<T> itr)
    {
        // convert the iterator into a Spliterator
        Spliterator<T> spitr = Spliterators.spliteratorUnknownSize(
                                           itr, Spliterator.NONNULL);

        // Convert spliterator into a sequential stream
        // The second parameter "false" passess whether 
        // the stream is to be created parallel or not
        return StreamSupport.stream(spitr, false);
    }

    public static void main(String[] args)
    {
        Iterator<String> iterator = Arrays.asList("G", "E", "E", 
                                               "K", "S").iterator();

        Stream<String> stream = iteratorToSequentialStream(iterator);

        System.out.println("Sequential Stream : " + 
                    stream.collect(Collectors.toList()));
    }
}
```

****Output:**

```java
Sequential Stream : [G, E, E, K, S]

```** *   ****Using Iterable.Spliterator()**: Spliterator is the key to create the sequential stream. Hence in this method also, Spliterator is used. But in this method, the source of Spliterator is set to an **Iterable** created from the **Iterator**.

    所以首先从迭代器中创建 Iterable。然后，拆分器作为**可迭代拆分器()**直接传递给**流()**方法。

    **程序:**

    ```java
    // Java program to create a Sequential Stream
    // from an Iterator

    import java.util.*;
    import java.util.stream.*;

    class GfG {
        // Function to create a sequential Stream
        // from an Iterator
        public static <T> Stream<T> 
                      iteratorToSequentialStream(Iterator<T> itr)
        {
            // Get an iterable from itr
            Iterable<T> itb = () -> itr;

            // Get spliterator() from iterable and then
            // Convert into a sequential stream.
            // The second parameter "false" passess whether the
            // stream is to be created parallel or not
            return StreamSupport.stream(itb.spliterator(), false);
        }

        public static void main(String[] args)
        {
            Iterator<String> iterator = Arrays.asList("G", "E", "E",
                                                "K", "S").iterator();

            Stream<String> stream = iteratorToSequentialStream(iterator);

            System.out.println("Sequential Stream : " +
                        stream.collect(Collectors.toList()));
        }
    }
    ```

    **Output:**

    ```java
    Sequential Stream : [G, E, E, K, S]

    ```**