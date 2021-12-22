# 检查树形图是否为空的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查树图是否为空/](https://www.geeksforgeeks.org/java-program-to-check-if-the-treemap-is-empty/)

Java 中的 TreeMap 与 AbstractMap 类一起用于实现[地图接口](https://www.geeksforgeeks.org/map-interface-java-examples/)和[导航地图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)。地图根据其键的自然顺序进行排序，或者通过地图创建时提供的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)进行排序，具体取决于使用的构造函数。

**方法:**

1.  Use [I *empty ()*](https://www.geeksforgeeks.org/map-isempty-method-in-java-with-examples/) method.
2.  Use [*size ()*](https://www.geeksforgeeks.org/mapsize-c-stl/) method.

**方法 1:** 使用[I*sEmpty()*T5】方法](https://www.geeksforgeeks.org/map-isempty-method-in-java-with-examples/)

TreeMap 类的 java.util.TreeMap.isEmpty()方法用于检查 TreeMap 是否为空。

**语法:**

```
TreeMap.isEmpty()
```

**参数:**该方法不取任何参数。

**返回值:**如果树形图为空，则该方法返回布尔值 true，否则返回 false。因此，如果 TreeMap 对象中至少有一个键值映射，它将返回 false，否则返回 True。

**示例:**

## Java

```
// Java Program to Check if the TreeMap is Empty
// using the isEmpty() method

// Importing TreeMap class of
// java.util package
import java.util.TreeMap;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Create an empty TreeMap
        TreeMap<Integer, String> tmap
            = new TreeMap<Integer, String>();

        // Check TreeMap is empty or not
        boolean isEmpty = tmap.isEmpty();
        System.out.println("Is tmap empty :  " + isEmpty);

        // Mapping string values to int keys
        tmap.put(1, "Geeks");
        tmap.put(2, "For");
        tmap.put(3, "skeeG");

        // Displaying the TreeMap
        System.out.println("The Mappings are: " + tmap);

        // Checking again TreeMap is empty or not
        isEmpty = tmap.isEmpty();

        // Display boolean output again
        // to show isEmpty() method functionality
        System.out.println("Is tmap empty : " + isEmpty);

    }
}
```

**输出**

```
Is tmap empty :  true
The Mappings are: {1=One, 2=Two}
Is tmap empty : false
```

**方法二:**使用 [*大小()*](https://www.geeksforgeeks.org/mapsize-c-stl/) 方法

TreeMap 类的[*Java . util . TreeMap . size()*](https://www.geeksforgeeks.org/treemap-size-method-in-java/)方法通过大小与 0 的比较来检查 TreeMap 是否为空。如果 TreeMap 为空，则该方法返回 True，否则返回 false。

**语法:**

```
(TreeMap.size() == 0) ;
```

**参数:**该方法不取任何参数。

**返回值:**如果树形图为空，则该方法返回布尔值 True，否则返回 false。

**示例:**

## Java

```
// Java Program to Check if the TreeMap is Empty
// and illustrating the size() method

// Importing TreeMap class of
// java.util package
import java.util.TreeMap;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Create an empty TreeMap
        TreeMap<Integer, String> tmap
            = new TreeMap<Integer, String>();

        // Check TreeMap is empty or not
        // Using size() method
        System.out.println("Is map empty : "
                           + (tmap.size() == 0));

        // Mapping string values to int keys
        // Custom inputs mapping
        tmap.put(1, "One");
        tmap.put(2, "Two");

        // Displaying the TreeMap
        System.out.println("The Mappings are: " + tmap);

        // Display boolean output again
        // to show size() method functionality
        System.out.println("Is map empty : "
                           + (tmap.size() == 0));
    }
}
```

**输出**

```
Is map empty : true
The Mappings are: {1=One, 2=Two}
Is map empty : false
```

**注意:**相同的操作可以用任何类型的带有变化的映射和不同数据类型的组合来执行。