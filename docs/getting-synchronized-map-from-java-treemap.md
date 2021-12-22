# 从 Java 树形图中获取同步图

> 原文:[https://www . geesforgeks . org/get-synchronized-map-from-Java-tree map/](https://www.geeksforgeeks.org/getting-synchronized-map-from-java-treemap/)

[**树形图**](https://www.geeksforgeeks.org/treemap-in-java/) 是 Java Collections 框架的一部分。Java TreeMap 包含基于键的值。实现了[导航](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/) 接口，扩展了[抽象映射](https://www.geeksforgeeks.org/abstractmap-in-java/)类。它提供了一种以排序顺序存储键值对的有效方法。Java TreeMap 只包含唯一的元素。它不能有空键，但可以有多个空值。TreeMap 保持元素的升序。同步是指控制多个线程对任意共享资源的访问。一次只能有一个线程访问同步的资源。Java TreeMap 是不同步的，我们必须显式同步它，以便在多**–**线程环境中使用它。

可以使用[**collections . synchronized map()**](https://www.geeksforgeeks.org/collections-synchronizedmap-method-in-java-with-examples/)**方法同步树形图。Collections 类的[*synchronized Map()*](https://www.geeksforgeeks.org/collections-synchronizedmap-method-in-java-with-examples/)方法将必须同步的 Map 作为参数，并返回线程安全的同步 Map。 **java.util.Collections** 类的 *synchronizedMap()* 方法用于返回由指定映射支持的同步(线程安全)映射。为了保证串行访问，通过返回的映射完成对后备映射的所有访问是至关重要的。**

****语法:****

```java
public static <K, V> Map<K, V> synchronizedMap(Map<K, V> m)
```

****参数:**该方法将**地图**作为参数“包裹”在同步地图中。**

****返回值:**该方法返回指定地图的**同步视图**。**

****实施:****

****例****

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate
// synchronization of TreeMap

// Importing all classes from
// java.util package
import java.util.*;

// Class
public class GFG {

    // Main driver method
    public static void main(String[] args) throws Exception
    {

        // Try block to check if any exception occurs
        try {

            // Step1: Creating a TreeMap object
            // Declaring object of string type
            TreeMap<String, String> treeMap
                = new TreeMap<String, String>();

            // Step2: Adding elements into the above Map
            // Custom inputs
            treeMap.put("1", "Welcome");
            treeMap.put("2", "To");
            treeMap.put("3", "Geeks");
            treeMap.put("4", "For");
            treeMap.put("5", "Geeks");

            // Printing all elements of the above Map object
            System.out.println("Map : " + treeMap);

            // Synchronizing the map using
            // synchronizedMap() method of Collection class
            Map<String, String> sMap
                = Collections.synchronizedMap(treeMap);

            // Printing the Collection
            System.out.println("Synchronized map is : "
                               + sMap);
        }

        // Catch block to handle the exceptions
        catch (IllegalArgumentException e) {

            // Displaying and printing the exception
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

****Output**

```java
Map : {1=Welcome, 2=To, 3=Geeks, 4=For, 5=Geeks}
Synchronized map is : {1=Welcome, 2=To, 3=Geeks, 4=For, 5=Geeks}
```**