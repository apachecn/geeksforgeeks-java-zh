# 用示例初始化 Java 中的静态映射

> 原文:[https://www . geesforgeks . org/initialize-a-static-map-in-Java-with-examples/](https://www.geeksforgeeks.org/initialize-a-static-map-in-java-with-examples/)

在本文中，用 Java 创建并初始化了一个[静态](https://www.geeksforgeeks.org/static-keyword-java/) [地图](https://www.geeksforgeeks.org/map-interface-java-examples/)。

A **静态地图**是定义为[静态](https://www.geeksforgeeks.org/static-keyword-java/)的地图。这意味着该映射成为一个类成员，可以使用类轻松使用。

*   **Method 1:**
    1.  创建静态映射变量。
    2.  在[静态块](https://www.geeksforgeeks.org/g-fact-79/)中实例化它。

    下面是上述方法的实现:

    ```
    // Java program to create a static map

    import java.util.*;

    class GFG {

        // Declaring the static map
        private static Map<Integer, String> map;

        // Instantiating the static map
        static
        {
            map = new HashMap<>();
            map.put(1, "GFG");
            map.put(2, "Geek");
            map.put(3, "GeeksForGeeks");
        }

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

*   **Method 2:** Creating a static map variable and instantiating it together.

    下面是上述方法的实现:

    ```
    // Java program to create a static map

    import java.util.*;

    class GFG {

        // Declaring the static map
        private static Map<Integer, String> map
            = new HashMap<>() {
                  map.put(1, "GFG");
                  map.put(2, "Geek");
                  map.put(3, "GeeksForGeeks");
              }

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