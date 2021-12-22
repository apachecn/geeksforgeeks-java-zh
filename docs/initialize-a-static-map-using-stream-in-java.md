# 使用 Java 中的流初始化静态地图

> 原文:[https://www . geesforgeks . org/initialize-a-static-map-using-stream-in-Java/](https://www.geeksforgeeks.org/initialize-a-static-map-using-stream-in-java/)

在本文中，使用[流](https://www.geeksforgeeks.org/stream-in-java/)在 Java 中创建和初始化了一个[静态](https://www.geeksforgeeks.org/static-keyword-java/) [地图](https://www.geeksforgeeks.org/map-interface-java-examples/)。

**Java 中的静态地图**
A **静态地图**是定义为[静态](https://www.geeksforgeeks.org/static-keyword-java/)的地图。这意味着该映射成为一个类成员，可以使用类轻松使用。

**[Java 中的 Stream](https://www.geeksforgeeks.org/stream-in-java/)**
在 Java 8 中引入了 Stream API，用于处理对象的集合。流是支持各种方法的对象序列，这些方法可以通过流水线来产生所需的结果。

**进场:**

*   创建一个流，并将 2D 值作为键和值对插入其中。
*   这些值稍后将用于实例化地图。
*   使用流的 collect()方法，将值从流映射到映射。
*   这可以分别借助 [Collectors.toMap()](https://www.geeksforgeeks.org/collectors-tomap-method-in-java-with-examples/) 方法以及 keyMapper 和 ValueMapper 来完成。

下面是上述方法的实现:

```java
// Java program to create a static map using Stream

import java.util.*;
import java.util.stream.Collectors;

class GFG {

    // Declaring and instantiating the static map
    private static Map<String, String> map
        = Arrays.stream(new String[][] {
                            { "1", "GFG" },
                            { "2", "Geek" },
                            { "3", "GeeksForGeeks" } })
              .collect(Collectors.toMap(
                  keyMapper -> keyMapper[0], valueMapper -> valueMapper[1]));

    // Driver code
    public static void main(String[] args)
    {
        System.out.println(map);
    }
}
```

**Output:**

```java
{1=GFG, 2=Geek, 3=GeeksForGeeks}

```