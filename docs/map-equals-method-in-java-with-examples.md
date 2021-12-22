# Java 中的 Map equals()方法，示例

> 原文:[https://www . geesforgeks . org/map-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/map-equals-method-in-java-with-examples/)

java 中的 java.util.Map.equals()方法用于检查两个映射之间的相等性。它验证作为参数传递的一个映射的元素是否等于这个映射的元素。

**语法:**

```java
boolean equals(object obj)
```

**参数:**该方法接受该地图类型的一个参数*对象*，并引用要用该地图检查其相等性的地图。

**返回值:**如果两个对象映射相等，则方法返回真，否则返回假。

下面的程序说明了 java.util.Map.equals()方法:
**程序 1:**

```java
// Java code to illustrate the equals() method
import java.util.*;

public class Map_Demo {
    public static void main(String[] args)
    {
        // Creating an empty Map
        Map<Integer, String> map1 = new HashMap<Integer, String>();
        Map<Integer, String> map2 = new HashMap<Integer, String>();

        // Mapping string values to int keys
        map1.put(10, "Geeks");
        map1.put(15, "4");
        map1.put(20, "Geeks");
        map1.put(25, "Welcomes");
        map1.put(30, "You");

        // Mapping string values to int keys
        map2.put(10, "Geeks");
        map2.put(15, "4");
        map2.put(20, "Geeks");
        map2.put(25, "Welcomes");
        map2.put(30, "You");

        // Displaying the Map1
        System.out.println("First Map: "
                           + map1);

        // Displaying the Map2
        System.out.println("Second Map: "
                           + map2);

        // Checking the equality
        System.out.println("Equality: " + map1.equals(map2));
    }
}
```

**Output:**

```java
First Map: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Second Map: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Equality: true

```

**程序 2:**

```java
// Java code to illustrate the equals() method
import java.util.*;

public class Map_Demo {
    public static void main(String[] args)
    {
        // Creating an empty Map
        Map<Integer, String> map1 = new HashMap<Integer, String>();
        Map<Integer, String> map2 = new HashMap<Integer, String>();

        // Mapping string values to int keys for map1
        map1.put(10, "Geeks");
        map1.put(15, "4");
        map1.put(20, "Geeks");
        map1.put(25, "Welcomes");
        map1.put(30, "You");

        // Mapping string values to int keys for map2
        map2.put(10, "Geeks");
        map2.put(15, "4");
        map2.put(20, "Geek");
        map2.put(25, "Welcomes");
        map2.put(30, "You");

        // Displaying the map 1
        System.out.println("First Map: " + map1);

        // Displaying the map 2
        System.out.println("Second Map: " + map2);

        // Displaying the equality
        System.out.println("Equality: " + map1.equals(map2));
    }
}
```

**Output:**

```java
First Map: {20=Geeks, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Second Map: {20=Geek, 25=Welcomes, 10=Geeks, 30=You, 15=4}
Equality: false

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/util/map . html # equals(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/util/Map.html#equals(java.lang.Object))