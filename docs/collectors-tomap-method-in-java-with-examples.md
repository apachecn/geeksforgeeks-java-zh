# Java 中的 Collectors toMap()方法，带示例

> 原文:[https://www . geesforgeks . org/collectors-tomap-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collectors-tomap-method-in-java-with-examples/)

**toMap()** 方法是 **Collectors** 类的静态方法，它返回一个 Collector，该 Collector 将元素累积到一个 Map 中，该 Map 的键和值是将提供的映射函数应用于输入元素的结果。请注意，键是唯一的，如果在任何情况下键都是重复的，那么在执行收集操作时会引发 IllegalStateException。

toMap()方法有 3 个重载:

### 函数键映射器，函数值映射器

**语法:**

```
public static  Collector<T, ?, Map>
    toMap(Function keyMapper, Function valueMapper)

```

在哪里

*   **T** :输入元素的类型。
*   **地图**:输出地图。
*   **接口收集器:**将输入元素累积到可变结果容器中的可变约简操作，可选地在所有输入元素处理完毕后将累积的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
*   **toMap()**:Collectors 类的静态方法，返回一个 Collector，它将元素收集到一个 Map 中，Map 的键和值是将映射函数应用于输入元素的结果。Collectors 类在 java.util.streams 包下。

**参数:**该方法接受以下参数:

*   **按键映射器**:产生按键的映射功能
*   **值映射器**:产生值的映射函数

**返回值:**该方法返回一个收集器，该收集器将元素收集到一个映射中，该映射的键和值是对输入元素应用映射函数的结果

下面的例子说明了上述方法:

```
// Java program to demonstrate
// toMap() method with unique keys

import java.util.stream.Collectors;
import java.util.stream.Stream;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create a String with no repeated keys
        Stream<String[]>
            str = Stream
                      .of(new String[][] { { "GFG", "GeeksForGeeks" },
                                           { "g", "geeks" },
                                           { "G", "Geeks" } });

        // Convert the String to Map
        // using toMap() method
        Map<String, String>
            map = str.collect(
                Collectors.toMap(p -> p[0], p -> p[1]));

        // Print the returned Map
        System.out.println("Map:" + map);
    }
}
```

**Output:**

```
Map:{G=Geeks, g=geeks, GFG=GeeksForGeeks}

```

### 函数键映射器、函数值映射器、二进制运算符<u>合并函数)</u>

这是 **toMap()** 方法的一个重载，其中一个额外的参数被添加到键和值中，这就是**合并函数**。该函数的任务是以编码器定义的方式合并具有相同键的值。仅当多个值有相同的键时，才建议使用此重载方法。下面给出一个简单的例子。

**语法:**

```
public static  Collector<T, ?, Map> 
    toMap(Function keyMapper, 
          Function valueMapper, 
          BinaryOperator<U> mergeFunction)

```

在哪里

*   **T** :输入元素的类型。
*   **地图**:输出地图。
*   **接口收集器:**将输入元素累积到可变结果容器中的可变约简操作，可选地在所有输入元素处理完毕后将累积的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
*   **toMap()**:Collectors 类的静态方法，返回一个 Collector，它将元素收集到一个 Map 中，Map 的键和值是将映射函数应用于输入元素的结果。Collectors 类在 java.util.streams 包下。

**参数:**该方法接受以下参数:

*   **按键映射器**:产生按键的映射功能
*   **值映射器**:产生值的映射函数
*   **合并函数**:一个合并函数，用于解决与同一个键相关的值之间的冲突，如提供给 Map.merge(对象，对象，双函数)

**返回值:**该方法返回一个 Collector，该 Collector 将元素收集到一个 Map 中，该 Map 的键是对输入元素应用键映射函数的结果，其值是对等于该键的所有输入元素应用值映射函数并使用合并函数组合它们的结果

下面的例子说明了上述方法:

```
// Java program to demonstrate
// toMap() method without unique keys

import java.util.stream.Collectors;
import java.util.stream.Stream;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Create a String with repeated keys
        Stream<String[]>
            str = Stream
                      .of(new String[][] { { "GFG", "GeeksForGeeks" },
                                           { "g", "geeks" },
                                           { "GFG", "geeksforgeeks" } });

        // Get Map from String
        // using toMap() method
        Map<String, String>
            map = str
                      .collect(Collectors
                                   .toMap(p -> p[0], p -> p[1], (s, a) -> s + ", " + a));

        // Print the Map
        System.out.println("Map:" + map);
    }
}
```

**Output:**

```
Map:{g=geeks, GFG=GeeksForGeeks, geeksforgeeks}

```

### 函数键映射器，函数值映射器，二进制运算符<u>合并函数，供应商映射供应商)</u>

这是带有附加参数 **toMap()** 的重载方法，即供应商。我们需要通过这里的供应商。Supplier 是 java.util.Function 类的接口。这是一个函数接口，因此可以用作 lambda 表达式或方法引用的赋值目标。如果要返回 LinkedHashMap，需要将供应商传递为 LinkedHashMap::new。在下面的例子中，我们也将这样做。

**语法:**

```
public static <T, K, U, M extends Map> Collector 
    toMap(Function keyMapper,
          Function valueMapper,
          BinaryOperator<U> mergeFunction,
          Supplier mapSupplier)

```

在哪里

*   **T** :输入元素的类型。
*   **地图**:输出地图。
*   **接口收集器:**将输入元素累积到可变结果容器中的可变约简操作，可选地在所有输入元素处理完毕后将累积的结果转换为最终表示。还原操作可以顺序执行，也可以并行执行。
*   **toMap()**:Collectors 类的静态方法，返回一个 Collector，它将元素收集到一个 Map 中，Map 的键和值是将映射函数应用于输入元素的结果。Collectors 类在 java.util.streams 包下。

**参数:**该方法接受以下参数:

*   **按键映射器**:产生按键的映射功能
*   **值映射器**:产生值的映射函数
*   **合并函数**:一个合并函数，用于解决与同一个键相关的值之间的冲突，如提供给 Map.merge(对象，对象，双函数)
*   **地图提供者**:返回一个新的空地图的函数，结果将被插入其中

**返回值:**该方法返回一个 Collector，该 Collector 将元素收集到一个 Map 中，该 Map 的键是对输入元素应用键映射函数的结果，其值是对等于该键的所有输入元素应用值映射函数并使用合并函数组合它们的结果

下面的例子说明了上述方法:

```
// Java program to demonstrate
// toMap() method

import java.util.stream.Collectors;
import java.util.stream.Stream;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Create a String to be converted
        Stream<String[]>
            Ss1 = Stream
                      .of(new String[][] { { "GFG", "GeeksForGeeks" },
                                           { "g", "geeks" },
                                           { "GFG", "Geeks" } });

        // Get Map from String
        // using toMap() method
        LinkedHashMap<String, String>
            map2 = Ss1
                       .collect(Collectors
                                    .toMap(
                                        p -> p[0], p -> p[1], (s, a) -> s + ", " + a, LinkedHashMap::new));

        // Print the Map
        System.out.println("Map:" + map2);
    }
}
```

**Output:**

```
Map:{GFG=GeeksForGeeks, Geeks, g=geeks}

```