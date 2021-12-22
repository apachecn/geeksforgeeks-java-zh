# 如何在 Java 中克隆地图

> 原文:[https://www.geeksforgeeks.org/how-to-clone-a-map-in-java/](https://www.geeksforgeeks.org/how-to-clone-a-map-in-java/)

给定一张地图，任务就是克隆这张地图。

以下是在 Java 中克隆[地图的 5 种不同方法。](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)

**示例:**

```java
{1=Geeks, 2=For, 3=Geeks}

```

*   **法 1:天真法**
    1。为类别映射创建一个对象。
    2。使用 Put()方法将元素放入地图中。
    3。再次为类映射创建另一个对象。
    4。现在最后迭代地图并调用 put 方法来克隆初始地图。

下面是上述方法的实现:

**实施:**

```java
// Program to clone a Map in Java
// Naive Method

import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Creating an object for class Map
        Map<Integer, String> hash_Map
            = new HashMap<Integer, String>();

        // putting elements into the map
        hash_Map.put(1, "Geeks");
        hash_Map.put(2, "For");
        hash_Map.put(3, "Geeks");

        // Creating a new object for
        // class Map to clone a map
        Map<Integer, String> new_map
            = new HashMap<Integer, String>();

        // using iterator
        for (Map.Entry<Integer, String> entry : hash_Map.entrySet()) {
            new_map.put(entry.getKey(),
                        entry.getValue());
        }

        System.out.println(new_map);
    }
}
```

**Output:**

```java
{1=Geeks, 2=For, 3=Geeks}

```

*   **Method 2: Using putAll().**
    1\. Create an object for the class map.
    2\. Put the elements into the map using the put() method.
    3\. Again create another object for the class map.
    4\. Now finally use putAll() method to clone the initial map.

    下面是上述方法的实现:

    **实施:**

    ```java
    // Program to clone a Map in Java
    // putAll Method

    import java.util.*;

    class GFG {

        public static void main(String[] args)
        {
            // Creating an object for class Map
            Map<Integer, String> hash_Map
                = new HashMap<Integer, String>();

            // Putting elements into the map
            hash_Map.put(1, "Geeks");
            hash_Map.put(2, "For");
            hash_Map.put(3, "Geeks");

            // Creating a new object
            // for class Map to clone a map
            Map<Integer, String> new_map
                = new HashMap<Integer, String>();

            // using putAll method
            new_map.putAll(hash_Map);

            System.out.println(new_map);
        }
    }
    ```

    **Output:**

    ```java
    {1=Geeks, 2=For, 3=Geeks}

    ```

    *   **方法 3:复制构造函数。**
    1。为类别映射创建一个对象。
    2。使用 Put()方法将元素放入地图中。
    3。再次为类映射创建另一个对象。
    4。现在，最后使用复制构造函数(它是一个特殊的构造函数，用于创建一个新对象作为现有对象的副本)来克隆初始地图。

下面是上述方法的实现:

**实施:**

```java
// Program to clone a Map in Java
// Copy Constructor

import java.util.*;

class GFG {

    public static void main(String[] args)
    {
        // Creating an object for class Map
        Map<Integer, String> hash_Map
            = new HashMap<Integer, String>();

        // putting elements into the map
        hash_Map.put(1, "Geeks");
        hash_Map.put(2, "For");
        hash_Map.put(3, "Geeks");

        // Creating a new object
        // for class Map to clone a map
        Map<Integer, String> new_map
            = new HashMap<Integer, String>();

        new_map = new HashMap<>(hash_Map);
        System.out.println(new_map);
    }
}
```

**Output:**

```java
{1=Geeks, 2=For, 3=Geeks}

```

*   **Method 4: Java 8**
    1\. Create an object for the class map.
    2\. Put the elements into the map using the put() method.
    3\. Again create another object for the class map.
    4\. Now finally use Stream API from Java 8 to clone the initial map.

    下面是上述方法的实现:

    **实施:**

    ```java
    // Program to clone a Map in Java
    // Using java8

    import java.util.*;
    import java.util.stream.Collectors;

    class GFG {

        public static void main(String[] args)
        {
            // Creating an object for class Map
            Map<Integer, String> hash_Map
                = new HashMap<Integer, String>();

            // putting elements into the map
            hash_Map.put(1, "Geeks");
            hash_Map.put(2, "For");
            hash_Map.put(3, "Geeks");

            // Creating a new object
            // for class Map to clone a map
            Map<Integer, String> new_map
                = new HashMap<Integer, String>();

            new_map
                = hash_Map.entrySet()
                      .stream()
                      .collect(
                          Collectors
                              .toMap(Map.Entry::getKey,
                                     Map.Entry::getValue));

            System.out.println(new_map);
        }
    }
    ```

    **Output:**

    ```java
    {1=Geeks, 2=For, 3=Geeks}

    ```

    **说明:**也和上面的方法类似，但是这里我们使用 java 8 中的 Stream API 来克隆原始地图。

    *   **Method 5: JSON**
    1\. Create an object for the class map.
    2\. Put the elements into the map using the put() method.
    3\. Again create another object for the class map.
    4\. Now finally use Google’s GSON library to clone the initial map.

    下面是上述方法的实现:

    **实施:**

    ```java
    // Program to clone a Map in Java
    // JSON Method

    import java.util.*;
    import java.util.stream.Collectors;
    import com.google.gson.Gson;

    class GFG {

        public static void main(String[] args)
        {
            // Creating an object for class Map
            Map<Integer, String> hash_Map
                = new HashMap<Integer, String>();

            // putting elements into the map
            hash_Map.put(1, "Geeks");
            hash_Map.put(2, "For");
            hash_Map.put(3, "Geeks");

            // Creating a new object
            // for class Map to clone a map
            Map<Integer, String> new_map
                = new HashMap<Integer, String>();
            Gson gson = new Gson();

            String jsonString = gson.toJson(hash_Map);

            new_map = gson.fromJson(jsonString, Map.class);

            System.out.println(new_map);
        }
    }
    ```

    **Output:**

    ```java
    {1=Geeks, 2=For, 3=Geeks}

    ```

    **说明:**也和上面的方法类似，但是这里我们用谷歌的 GSON 库来克隆原始地图。在这里，我们首先将 map 转换为一个 JSON 字符串，然后将该字符串转换为一个新的 Map。