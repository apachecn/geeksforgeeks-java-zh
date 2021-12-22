# 使用 Java 9 Map.of()初始化静态映射

> 原文:[https://www . geesforgeks . org/initialize-a-static-map-using-Java-9-map-of/](https://www.geeksforgeeks.org/initialize-a-static-map-using-java-9-map-of/)

在本文中，使用 Java 9 在 Java 中创建并初始化了一个[静态](https://www.geeksforgeeks.org/static-keyword-java/) [地图](https://www.geeksforgeeks.org/map-interface-java-examples/)。

**Java 中的静态地图**
A **静态地图**是定义为[静态](https://www.geeksforgeeks.org/static-keyword-java/)的地图。这意味着该映射成为一个类成员，可以使用类轻松使用。

**[Java 9 特性–Map . of()方法](https://www.geeksforgeeks.org/factory-method-create-immutable-map-java-9/)**
在 [Java 9 中，引入了 Map.of()](https://www.geeksforgeeks.org/factory-method-create-immutable-map-java-9/) ，这是一种创建 Map 接口实例的便捷方式。它最多可以容纳 10 个键值对。

**进场:**

*   在 Map.of()方法中将映射值作为键和值对传递。
*   返回静态工厂映射实例。
*   将其存储在地图中并使用。

下面是上述方法的实现:

**例 1:**

```
// Java program to create a static map using Java 9

import java.util.*;

class GFG {

    // Declaring and instantiating the static map
    private static Map<String, String> map
        = Map.of("1", "GFG",
                 "2", "Geek",
                 "3", "GeeksForGeeks");

    // Driver code
    public static void main(String[] args)
    {
        System.out.println(map);
    }
}
```

**输出:**

```
{3=GeeksForGeeks, 2=Geek, 1=GFG}

```

**示例 2:** 显示给出 10 个键值对时的错误

```
// Java program to create a static map using Java 9

import java.util.*;

class GFG {

    // Declaring and instantiating the static map
    private static Map<String, String> map
        = Map.of("1", "GFG",
                 "2", "Geek",
                 "3", "GeeksForGeeks",
                 "4", "G",
                 "5", "e",
                 "6", "e",
                 "7", "k",
                 "8", "s",
                 "9", "f",
                 "10", "o");

    // Driver code
    public static void main(String[] args)
    {
        System.out.println(map);
    }
}
```

**输出:**

```
{10=o, 9=f, 8=s, 7=k, 6=e, 5=e, 4=G, 3=GeeksForGeeks, 2=Geek, 1=GFG}

```

**示例 3:** 显示给出 10 个以上键值对时的错误

```
// Java program to create a static map using Java 9

import java.util.*;

class GFG {

    // Declaring and instantiating the static map
    private static Map<String, String> map
        = Map.of("1", "GFG",
                 "2", "Geek",
                 "3", "GeeksForGeeks",
                 "4", "G",
                 "5", "e",
                 "6", "e",
                 "7", "k",
                 "8", "s",
                 "9", "f",
                 "10", "o",
                 "11", "r");

    // Driver code
    public static void main(String[] args)
    {
        System.out.println(map);
    }
}
```

**编译错误:**

```
Main.java:12: error: no suitable method found for
 of(String, String,
    String, String,
    String, String,
    String, String,
    String, String,
    String, String,
    String, String,
    String, String,
    String, String,
    String, String,
    String, String)

1 error

```

**相关文章:**

*   [用示例初始化 Java 中的静态映射](https://www.geeksforgeeks.org/initialize-a-static-map-in-java-with-examples/)
*   [使用 Java 中的流初始化静态地图](https://www.geeksforgeeks.org/initialize-a-static-map-using-stream-in-java/)