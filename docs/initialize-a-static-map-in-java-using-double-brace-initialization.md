# 使用双支撑初始化

在 Java 中初始化静态地图

> 原文:[https://www . geesforgeks . org/initialize-a-static-map-in-Java-using-double-brake-initialization/](https://www.geeksforgeeks.org/initialize-a-static-map-in-java-using-double-brace-initialization/)

在本文中，一个[静态](https://www.geeksforgeeks.org/static-keyword-java/) [地图](https://www.geeksforgeeks.org/map-interface-java-examples/)被创建并使用双支撑初始化在 Java 中初始化。

**[Java 中的静态地图](https://www.geeksforgeeks.org/initialize-a-static-map-in-java-with-examples/)**
A **静态地图**是定义为[静态](https://www.geeksforgeeks.org/static-keyword-java/)的地图。这意味着该映射成为一个类成员，可以使用类轻松使用。

**[双支撑初始化](https://www.geeksforgeeks.org/double-brace-initialization-java/)**
在双支撑初始化中:

*   第一个大括号创建了一个新的[匿名内部类](https://www.geeksforgeeks.org/anonymous-inner-class-java/)。这些内部类能够访问其父类的行为。所以，在我们的例子中，我们实际上是在创建 [HashMap 类](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)的子类，所以这个[内部类](https://www.geeksforgeeks.org/inner-class-java/)能够使用 put()方法。
*   第二个大括号是[实例初始值设定项](https://www.geeksforgeeks.org/instance-initialization-block-iib-java/)。每当创建实例时，都会执行实例初始值设定项中的代码。

**进场:**

*   将映射值作为键和值对传递到[双括号](https://www.geeksforgeeks.org/double-brace-initialization-java/)中。
*   返回静态工厂映射实例。
*   将其存储在地图中并使用。

下面是上述方法的实现:

**例 1:**

```
// Java program to create a static map
// using Double Brace Initialization

import java.util.*;

class GFG {

    // Declaring and instantiating the static map
    // using Double Brace Initialization
    private static Map<String, String> map
        = new HashMap<String, String>() {{
            put("1", "GFG");
            put("2", "Geek");
            put("3", "GeeksForGeeks");
        }};

    // Driver code
    public static void main(String[] args)
    {
        System.out.println(map);
    }
}
```

**Output:**

```
{1=GFG, 2=Geek, 3=GeeksForGeeks}

```

**示例 2:** 用 10 个键值对显示

```
// Java program to create a static map
// using Double Brace Initialization

import java.util.*;

class GFG {

    // Declaring and instantiating the static map
    // using Double Brace Initialization
    private static Map<String, String> map
        = new HashMap<String, String>() {{
            put("1", "GFG");
            put("2", "Geek");
            put("3", "GeeksForGeeks");
            put("4", "G");
            put("5", "e");
            put("6", "e");
            put("7", "k");
            put("8", "s");
            put("9", "f");
            put("10", "o");
        }};

    // Driver code
    public static void main(String[] args)
    {
        System.out.println(map);
    }
}
```

**Output:**

```
{1=GFG, 2=Geek, 3=GeeksForGeeks, 4=G, 5=e, 6=e, 7=k, 8=s, 9=f, 10=o}

```

**相关文章:**

*   [用示例初始化 Java 中的静态映射](https://www.geeksforgeeks.org/initialize-a-static-map-in-java-with-examples/)
*   [使用 Java 中的流初始化静态地图](https://www.geeksforgeeks.org/initialize-a-static-map-using-stream-in-java/)
*   [使用 Java 9 Map.of()初始化静态映射](https://www.geeksforgeeks.org/initialize-a-static-map-using-java-9-map-of/)