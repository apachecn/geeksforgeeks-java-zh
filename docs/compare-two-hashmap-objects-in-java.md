# 比较 Java 中的两个 HashMap 对象

> 原文:[https://www . geesforgeks . org/compare-two-hashmap-objects-in-Java/](https://www.geeksforgeeks.org/compare-two-hashmap-objects-in-java/)

在本文中，我们将学习如何在 Java 中比较两个**[**HashMap**](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)**对象。在 [**java.util** 包](https://www.geeksforgeeks.org/java-util-package-java/)中存在 HashMap 类。HashMap 用于存储键值对，因此有不同的场景来比较 HashMap 的两个 Objects。以下哪一项:****

1.  ****比较条目****
2.  ****比较密钥****
3.  ****比较值****

******示例:******

```java
****Input :** HashMapA = [a=1, b=2], HashMapB = [a=1, c=2]
**Output:**
    Compare Entry = Not Equal
    Compare Keys = Not Equal
    Compare values = Equal**
```

******1** 。**对比**[T5】条目](https://www.geeksforgeeks.org/map-entry-interface-java-example/)T8:****

****条目是键值对。我们可以通过将条目与地图的 [**equals()**](https://www.geeksforgeeks.org/overriding-equals-method-in-java/) 方法进行比较来比较两个哈希表，如果地图具有相同的键值对，则意味着相同的条目。****

****下面是实现:****

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java program to compare two HashMap objects
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // New HashMap1
        HashMap<Integer, String> map1 = new HashMap<>();

        // Add Entry to map
        map1.put(1, "Akshay");
        map1.put(2, "Bina");
        map1.put(3, "Chintu");

        // New HashMap2
        HashMap<Integer, String> map2 = new HashMap<>();

        // Add Entry to map
        map2.put(3, "Chintu");
        map2.put(2, "Bina");
        map2.put(1, "Akshay");

        // New HashMap3
        HashMap<Integer, String> map3 = new HashMap<>();

        // Add Entry to map
        map3.put(1, "Akshay");
        map3.put(2, "Binod");
        map3.put(3, "Chintu");

        // Compare map1 and map2
        System.out.println("map1 == map2 : "
                           + map1.equals(map2));

        // Compare map1 and map3
        System.out.println("map1 == map3 : "
                           + map1.equals(map3));
    }
}**
```

******Output**

```java
map1 == map2 : true
map1 == map3 : false
```**** 

******2。** **比较键:******

****我们可以通过比较使用 [**键集()**](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/) 方法获得的键来检查两个 HashMap 对象是否有相同的键。我们用 [**等于()**](https://www.geeksforgeeks.org/overriding-equals-method-in-java/) 的方法设置比较键。****

****下面是实现:****

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java program to compare two HashSet keys
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // New HashMap1
        HashMap<Integer, String> map1 = new HashMap<>();

        // Add Entry to map
        map1.put(1, "Akshay");
        map1.put(2, "Bina");
        map1.put(3, "Chintu");

        // New HashMap2
        HashMap<Integer, String> map2 = new HashMap<>();

        // Add Entry to map
        map2.put(3, "Chintu");
        map2.put(2, "Bina");
        map2.put(1, "Akshay");

        // New HashMap3
        HashMap<Integer, String> map3 = new HashMap<>();

        // Add Entry to map
        map3.put(1, "Akshay");
        map3.put(2, "Binod");
        map3.put(4, "Chintu");

        // Compare map1 and map2 keys using keySet() and
        // equals() method
        System.out.println(
            "map1 keys == map2 keys : "
            + map1.keySet().equals(map2.keySet()));

        // Compare map1 and map3 keys using keySet() and
        // equals() method
        System.out.println(
            "map1 keys == map3 keys : "
            + map1.keySet().equals(map3.keySet()));
    }
}**
```

******Output**

```java
map1 keys == map2 keys : true
map1 keys == map3 keys : false
```**** 

******3。** **比较数值:******

****通过使用 [**值()**](https://www.geeksforgeeks.org/hashmap-values-method-in-java/) 方法将所有地图值转换为集合，然后将值与集合的**[**equals()**](https://www.geeksforgeeks.org/overriding-equals-method-in-java/)**方法进行比较，我们可以比较地图对象中包含的值是否相同。********

******下面是实现:******

## ******Java 语言(一种计算机语言，尤用于创建网站)******

```java
****// Java program to compare HashMap values
import java.util.*;

class GFG {
    public static void main(String[] args)
    {

        // New HashMap1
        HashMap<Integer, String> map1 = new HashMap<>();

        // Add Entry to map
        map1.put(1, "Akshay");
        map1.put(2, "Bina");
        map1.put(3, "Chintu");

        // New HashMap2
        HashMap<Integer, String> map2 = new HashMap<>();

        // Add Entry to map
        map2.put(3, "Chintu");
        map2.put(2, "Bina");
        map2.put(1, "Akshay");

        // New HashMap3
        HashMap<Integer, String> map3 = new HashMap<>();

        // Add Entry to map
        map3.put(1, "Akshay");
        map3.put(2, "Binod");
        map3.put(3, "Shinchain");

        // Value set of map1
        HashSet<String> set1 = new HashSet<>(map1.values());

        // Value set of map2
        HashSet<String> set2 = new HashSet<>(map2.values());

        // Value set of map3
        HashSet<String> set3 = new HashSet<>(map3.values());

        // Compare map1 and map2 values using equals()
        // method
        System.out.println("map1 values == map2 values : "
                           + set1.equals(set2));

        // Compare map1 and map3 values using equals()
        // method
        System.out.println("map1 values == map3 values : "
                           + set1.equals(set3));
    }
}****
```

********Output**

```java
map1 values == map2 values : true
map1 values == map3 values : false
```******