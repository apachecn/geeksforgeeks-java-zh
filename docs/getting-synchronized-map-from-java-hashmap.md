# 从 Java HashMap 获取同步地图

> 原文:[https://www . geesforgeks . org/get-synchronized-map-from-Java-hashmap/](https://www.geeksforgeeks.org/getting-synchronized-map-from-java-hashmap/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/#:~:text=HashMap%20is%20similar%20to%20the,you%20need%20to%20import%20java.) 是非同步集合类。如果我们想对它执行线程安全的操作，那么我们必须显式地同步它。为了显式地同步它，[**synchronized map()**](https://www.geeksforgeeks.org/collections-synchronizedmap-method-in-java-with-examples/)方法的[**Java . util . collections**](https://www.geeksforgeeks.org/collections-in-java-2/)类用于返回由指定映射支持的同步(线程安全)映射。

```java
// Get synchronized map using Collections.synchronizedMap()

Map<Integer, String> synchrMap = Collections.synchronizedMap(hmap);
```

**为了迭代同步地图，我们使用** [**同步块**](https://www.geeksforgeeks.org/method-block-synchronization-java/) **:**

```java
// Synchronized block
synchronized (synchrMap) {

      // Iterate synchronized map
      for (Map.Entry<Integer, String> entry : synchrMap.entrySet()) {

        // Print key : value
        System.out.println(entry.getKey() + " : " + entry.getValue());

      }
}
```

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to demonstrate how 
// to get synchronized map from HashMap

import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // New HashMap
        HashMap<Integer, String> hmap = new HashMap<>();

        // Add element to map
        hmap.put(1, "Akshay");
        hmap.put(2, "Bina");
        hmap.put(3, "Chintu");

        // Get synchronized map using
        // Collections.synchronizedMap()
        Map<Integer, String> synchrMap = Collections.synchronizedMap(hmap);

        System.out.println("Synchronized Map : ");

        // Synchronized block
        synchronized (synchrMap)
        {

            // Iterate synchronized map
            for (Map.Entry<Integer, String> entry :
                 synchrMap.entrySet()) {

                // Print key : value
                System.out.println(entry.getKey() + " : "
                                   + entry.getValue());
            }
        }
    }
}
```

**Output**

```java
Synchronized Map : 
1 : Akshay
2 : Bina
3 : Chintu
```