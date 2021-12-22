# Java 中的收集器分区 By()方法

> 原文:[https://www . geesforgeks . org/collectors-partitioning by-method-in-Java/](https://www.geeksforgeeks.org/collectors-partitioningby-method-in-java/)

**Collectors partitioning by()**方法是 java.util.stream.Collectors 类的预定义方法，用于根据给定的谓词对对象流(或一组元素)进行分区。该方法有两种重载变体。一个只接受谓词作为参数，而另一个同时接受谓词和收集器实例作为参数。

### partitioningBy(谓词 super T>谓词)

**语法:**

> 公共静态<t>收集器<t map="" list="">> >分区 By(谓词 super T>谓词)</t></t>

哪里，

*   **接口收集器< **T、A、R** >** :一种将输入元素累加到一个可变结果容器中的可变约简操作，可选地在所有输入元素都被处理之后将累加的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
    *   **T:** 归约运算的输入元素类型。
    *   **A:** 还原操作的可变累加类型。
    *   **R:** 归约运算的结果类型。
*   **地图<布尔，列表<T>T7:**包含输出的地图。键是布尔值(真或假)，对应的值是包含类型为 **T** 的元素的列表。

**参数:**该方法采用强制参数**谓词**，它是类型为 **T** 的谓词接口的实例。

**返回值:**该方法返回一个执行分区操作的**收集器**。

下面是一个说明 partitioningBy()方法的示例:

**程序:**

```java
// Java code to show the implementation of
// Collectors partitioningBy() function

import java.util.List;
import java.util.Map;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class Gfg {

    // Driver code
    public static void main(String[] args)
    {
        // creating an Integer stream
        Stream<Integer>
            s = Stream.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // using Collectors partitioningBy()
        // method to split the stream of elements into
        // 2 parts, greater than 3 and less than 3.
        Map<Boolean, List<Integer> >
            map = s.collect(
                Collectors.partitioningBy(num -> num > 3));

        // Displaying the result as a map
        // true if greater than 3, false otherwise
        System.out.println("Elements in stream "
                           + "partitioned by "
                           + "less than equal to 3: \n"
                           + map);
    }
}
```

**Output:**

```java
Elements in stream partitioned by less than equal to 3: 
{false=[1, 2, 3], true=[4, 5, 6, 7, 8, 9, 10]}

```

### 划分依据(谓词 super T>谓词，收集器 super T, A, D>下游)

**语法:**

> 公共静态<t>收集器<t map="" list="">> >分区 By(谓词 super T>谓词，收集器 super T, A, D>下游)</t></t>

哪里，

*   **接口收集器< **T、A、R** >** :一种将输入元素累加到一个可变结果容器中的可变约简操作，可选地在所有输入元素都被处理之后将累加的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
    *   **T:** 归约运算的输入元素类型。
    *   **A:** 还原操作的可变累加类型。
    *   **R:** 归约运算的结果类型。
*   **地图<布尔，列表<T>T7:**包含输出的地图。键是布尔值(真或假)，对应的值是包含类型为 **T** 的元素的列表。

**参数:**该方法取两个参数 a **谓词**，它是类型为 **T** 的谓词接口的一个实例，以及一个用于实现“下游约简”并产生输出的收集器。

**返回值:**该方法返回一个执行分区操作的**收集器**。

下面是说明 partitioningBy()方法的类型 2 的示例:

```java
// Java code to show the implementation of
// Collectors partitioningBy() function

import java.util.List;
import java.util.Map;
import java.util.stream.Collectors;
import java.util.stream.Stream;

class ArraytoArrayList {

    // Driver code
    public static void main(String[] args)
    {
        // creating an Integer stream
        Stream<Integer>
            s = Stream.of(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);

        // Using Collectors.counting() method
        // to count the number of elements in
        // the 2 partitions
        Map<Boolean, Long>
            map = s.collect(
                Collectors.partitioningBy(
                    num -> (num > 3), Collectors.counting()));

        // Displaying the result as a map
        // true if greater than 3, false otherwise
        System.out.println("Elements in stream "
                           + "partitioned by "
                           + "less than equal to 3: \n"
                           + map);
    }
}
```

**Output:**

```java
Elements in stream partitioned by less than equal to 3: 
{false=3, true=7}

```