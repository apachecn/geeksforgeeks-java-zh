# 在 Java 中寻找集合的最小和最大元素

> 原文:[https://www . geesforgeks . org/find-Java 中集合的最小和最大元素/](https://www.geeksforgeeks.org/finding-minimum-and-maximum-element-of-a-collection-in-java/)

一个[集合](https://www.geeksforgeeks.org/collections-in-java-2/)是表示为单个单元的一组单个对象。Java 提供了[集合框架](https://www.geeksforgeeks.org/java-collection-tutorial/)，它定义了几个类和接口来将一组对象表示为一个单元。这些是:

![](img/2205a548e21d55aa16fcce9ae90b203b.png)

使用 Collections.min()和 Collections.max()方法可以很容易地找到集合的最小和最大元素。这些是 Java 中集合类的静态方法。因此，它们可以通过类名直接访问，如下所示。

```java
Object ob = Collections.min(Collection<E> c);
Object ob = Collections.max(Collection<E> c);

```

如上面的语法所示，Collections.min()和 Collections.max()方法将 Collection 作为参数。这是要找到最大/最小元素的集合。因此，任何实现集合接口的类都可以作为参数在这些函数中传递，如数组、链表、数组列表、集合等。因此，任何集合的最大和最小元素都很容易找到。

下面的示例演示了查找一些集合的最小和最大元素的过程。

**例 1:** 在列表中

```java
// Java program to find the minimum and
// maximum element in a List

import java.util.*;

public class GFG {
    public static void main(String args[]) throws Exception
    {

        // Get the ArrayList
        List<Integer> list = new ArrayList<Integer>();

        // populate the list
        list.add(12);
        list.add(53);
        list.add(30);
        list.add(8);

        // printing the List
        System.out.println("List: " + list);

        // getting minimum value
        // using min() method
        int minList = Collections.min(list);

        // getting maximum value
        // using max() method
        int maxList = Collections.max(list);

        // printing the minimum value
        System.out.println("Minimum value of list is: "
                           + minList);

        // printing the maximum value
        System.out.println("Maximum value of list is: "
                           + maxList);
    }
}
```

**Output:**

```java
List: [12, 53, 30, 8]
Minimum value of list is: 8
Maximum value of list is: 53

```

**示例 2:** 成套

```java
// Java program to find the minimum and
// maximum element in a Set

import java.util.*;

public class GFG {
    public static void main(String args[]) throws Exception
    {

        // Get the HashSet
        Set<Integer> set = new HashSet<Integer>();

        // fill the hashSet
        set.add(3);
        set.add(6);
        set.add(2);
        set.add(9);

        // printing the Set
        System.out.println("Set: " + set);

        // getting minimum value
        // using min() method
        int minSet = Collections.min(set);

        // getting maximum value
        // using max() method
        int maxSet = Collections.max(set);

        // printing the minimum value
        System.out.println("Minimum value of set is: "
                           + minSet);

        // printing the maximum value
        System.out.println("Maximum value of set is: "
                           + maxSet);
    }
}
```

**Output:**

```java
Set: [2, 3, 6, 9]
Minimum value of set is: 2
Maximum value of set is: 9

```

**示例 3:** 在数组中

```java
// Java program to find the minimum and
// maximum element in an Array

import java.util.*;

public class GFG {
    public static void main(String args[]) throws Exception
    {

        // Get the Array
        Integer arr[] = { 2, 5, 1, 8, 34, 20, 4 };

        // printing the Array
        System.out.println("Array: " + Arrays.toString(arr));

        // getting minimum value
        // using min() method
        int minArray = Collections.min(Arrays.asList(arr));

        // getting maximum value
        // using max() method
        int maxArray
            = Collections.max(Arrays.asList(arr));

        // printing the minimum value
        System.out.println("Minimum value of Array is: "
                           + minArray);

        // printing the maximum value
        System.out.println("Maximum value of Array is: "
                           + maxArray);
    }
}
```

**Output:**

```java
Array: [2, 5, 1, 8, 34, 20, 4]
Minimum value of Array is: 1
Maximum value of Array is: 34

```

### 如果集合是地图，会发生什么？

Map 是 Java Collection Framework 中不同类型的实体，其中元素被视为<key value="">对，而不是直接值。所以地图采集类**不实现采集接口**。他们改为实现**地图界面**。因此 Collection.min()和 Collection.max()不适用于地图，并将抛出**编译错误**。</key>

**示例:**

```java
// Java program to find the minimum and
// maximum element in a Map

import java.util.*;

public class GFG {
    public static void main(String args[]) throws Exception
    {

        try {

            // Creating hashMap
            Map<String, Integer> map
                = new HashMap<String, Integer>();

            // Putting key-value pairs in map
            map.put("A", 10);
            map.put("B", 15);
            map.put("C", 20);
            map.put("D", 25);

            // Print the map
            System.out.println("Map: " + map);

            // getting minimum value using min()
            int minMap = Collections.min(map);

            // getting maximum value using max()
            int maxMap = Collections.max(map);

            // printing the minimum value
            System.out.println("Minimum value of Map is: "
                               + minMap);

            // printing the maximum value
            System.out.println("Maximum value of Map is: "
                               + maxMap);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception: " + e);
        }
    }
}
```

**Output:**

```java
Compile Errors:
prog.java:25: error: 
no suitable method found for min(Map)
            int minMap = Collections.min(map);
                                    ^
method Collections.<t>min(Collection) 
is not applicable</t> 
```

### 如何求地图的最小和最大元素？

虽然地图不实现采集接口，但是地图的元素类型**键**和**值**类**分别实现采集接口**。因此，最小和最大元素可以根据它们的键或值在地图中找到。

**示例 1:** 根据键值查找地图的最小和最大元素。

```java
// Java program to find the minimum and
// maximum element in a Map

import java.util.*;

public class GFG {
    public static void main(String args[]) throws Exception
    {

        // Creating hashMap
        Map<String, Integer> map
            = new HashMap<String, Integer>();

        // Putting key-value pairs in map
        map.put("A", 10);
        map.put("B", 15);
        map.put("C", 20);
        map.put("D", 25);

        // Print the map
        System.out.println("Map: " + map);

        // getting minimum value using min()
        String minKey = Collections.min(map.keySet());

        // getting maximum value using max()
        String maxKey = Collections.max(map.keySet());

        // printing the minimum value
        System.out.println("Minimum Key of Map is: "
                           + minKey);
        System.out.println("Value corresponding to "
                           + "minimum Key of Map is: "
                           + map.get(minKey));

        // printing the maximum value
        System.out.println("Maximum Key of Map is: " + maxKey);
        System.out.println("Value corresponding to "
                           + "maximum Key of Map is: "
                           + map.get(maxKey));
    }
}
```

**Output:**

```java
Map: {A=10, B=15, C=20, D=25}
Minimum Key of Map is: A
Value corresponding to minimum Key of Map is: 10
Maximum Key of Map is: D
Value corresponding to maximum Key of Map is: 25

```

**示例 2:** 根据值键查找地图的最小和最大元素。

```java
// Java program to find the minimum and
// maximum element in a Map

import java.util.*;

public class GFG {
    public static void main(String args[]) throws Exception
    {

        // Creating hashMap
        Map<String, Integer> map
            = new HashMap<String, Integer>();

        // Putting key-value pairs in map
        map.put("A", 10);
        map.put("B", 15);
        map.put("C", 20);
        map.put("D", 25);

        // Print the map
        System.out.println("Map: " + map);

        // getting minimum value using min()
        int minValue = Collections.min(map.values());

        // getting maximum value using max()
        int maxValue = Collections.max(map.values());

        // printing the minimum value
        System.out.println("Minimum Value of Map is: "
                           + minValue);

        // printing the maximum value
        System.out.println("Maximum Value of Map is: "
                           + maxValue);
    }
}
```

**Output:**

```java
Map: {A=10, B=15, C=20, D=25}
Minimum Value of Map is: 10
Maximum Value of Map is: 25

```