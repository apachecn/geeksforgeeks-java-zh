# 收集器收集 Java 中的 ten()方法，示例

> 原文:[https://www . geeksforgeeks . org/collectors-collectingandtheen-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collectors-collectingandthen-method-in-java-with-examples/)

Java 中**类收集器的**collecting ten(收集器下游，函数整理器)**方法，采用**收集器**，这样我们就可以执行额外的整理转换。**

**语法:**

```
public static <T, A, R, RR> 
       Collector <T, A, RR> 
       collectingAndThen(Collector <T, A, R> downstream, 
                         Function <R, RR> finisher)

Where,

```

*   **T** :输入元素的类型*   **A** :下游收集器的中间堆积型*   **R** :下游采集器的结果类型*   **RR** :结果收集器的结果类型

**参数:**该方法接受下面列出的两个参数

*   **下游:**它是一个收集器的实例，也就是说我们可以在这里使用任何收集器。*   **finisher:** It is an instance of a function which is to be applied to the final result of the downstream collector.

    **返回:**返回一个收集器，该收集器在整理器功能的帮助下，执行下游收集器的动作，然后是附加的整理步骤。

    下面是一些例子来说明**集合**的方法。

    **示例 1:** 创建不可变列表

    ```
    // Write Java code here
    // Collectors collectingAndThen() method

    import java.util.Collections;
    import java.util.List;
    import java.util.stream.Collectors;
    import java.util.stream.Stream;

    public class GFG {
        public static void main(String[] args)
        {
            // Create an Immutable List
            List<String> lt
                = Stream
                      .of("GEEKS", "For", "GEEKS")
                      .collect(Collectors
                                   .collectingAndThen(
                                       Collectors.toList(),
                                       Collections::<String> unmodifiableList));
            System.out.println(lt);
        }
    }
    ```

    **Output:**

    ```
    [GEEKS, For, GEEKS]

    ```

    **示例 2:** 创建不可移植集。

    ```
    // Write Java code here
    import java.util.Collections;
    import java.util.List;
    import java.util.Set;
    import java.util.stream.Collectors;
    import java.util.stream.Stream;

    public class GFG {
        public static void main(String[] args)
        {
            // Create an Immutable Set
            Set<String> st
                = Stream
                      .of("GEEKS", "FOR", "GEEKS")
                      .collect(
                          Collectors
                              .collectingAndThen(Collectors.toSet(),
                                                 Collections::<String>
                                                     unmodifiableSet));
            System.out.println(st);
        }
    }
    ```

    **Output:**

    ```
    [GEEKS, FOR]

    ```

    **示例 2:** 创建不可变地图

    ```
    import java.util.*;

    public class GFG {
        public static void main(String[] args)
        {
            // Create an Immutable Map
            Map<String, String> mp
                = Stream
                      .of(new String[][] {
                          { "1", "Geeks" },
                          { "2", "For" },
                          { "3", "Geeks" } })
                      .collect(
                          Collectors
                              .collectingAndThen(
                                  Collectors.toMap(p -> p[0], p -> p[1]),
                                  Collections::<String, String>
                                      unmodifiableMap));
            System.out.println(mp);
        }
    }
    ```

    **Output:**

    ```
    {1=Geeks, 2=For, 3=Geeks}

    ```

    **注意:**这个方法最常用于创建不可变集合。