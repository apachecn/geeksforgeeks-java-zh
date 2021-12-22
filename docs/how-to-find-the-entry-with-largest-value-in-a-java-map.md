# 如何在 Java 地图中找到值最大的条目

> 原文:[https://www . geesforgeks . org/如何找到 java 地图中价值最大的条目/](https://www.geeksforgeeks.org/how-to-find-the-entry-with-largest-value-in-a-java-map/)

给定一个 Java 中的[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)，任务是找出这个地图中值最高的条目。

插图:

```
Input  : Map = {ABC = 10, DEF = 30, XYZ = 20}
Output : DEF = 30
```

```
Input  : Map = {1 = 40, 2 = 30, 3 = 60}
Output : 3 = 60
```

**方法:**实现目标可以有以下几种途径:

1.  每个循环的简单迭代方法
2.  使用集合类中的 max()方法
3.  使用 Java 8 中引入的流概念

现在我们将讨论上面提出的方法和过程，并通过干净的 java 程序实现它们。

**方法 1:** 对每个循环使用迭代方法

**进场:**

1.  [通过条目](https://www.geeksforgeeks.org/iterate-map-java/)迭代地图条目
2.  将第一个条目存储在引用变量中，以便最初进行比较。
3.  如果当前条目的值大于引用条目的值，则将当前条目存储为引用条目。
4.  对地图中的所有条目重复此过程。
5.  最后，引用变量具有映射中最高值的必需条目。
6.  打印此条目

```
for (Map.Entry entry : map.entrySet()) 
{ // Operations }
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Find Entry
// with the Highest Value in Map
// Using Comparators in Map interface

// Importing all utility classes
import java.util.*;

// Main class
class GFG {

    // Method 1
    // Find the entry with highest value
    public static <K, V extends Comparable<V> >
        Map.Entry<K, V>
        getMaxEntryInMapBasedOnValue(Map<K, V> map)
    {

        // To store the result
        Map.Entry<K, V> entryWithMaxValue = null;

        // Iterate in the map to find the required entry
        for (Map.Entry<K, V> currentEntry :
             map.entrySet()) {

            if (
                // If this is the first entry, set result as
                // this
                entryWithMaxValue == null

                // If this entry's value is more than the
                // max value Set this entry as the max
                || currentEntry.getValue().compareTo(
                       entryWithMaxValue.getValue())
                       > 0) {

                entryWithMaxValue = currentEntry;
            }
        }

        // Return the entry with highest value
        return entryWithMaxValue;
    }

    // Method 2
    // To print the map
    public static void print(Map<String, Integer> map)
    {

        System.out.print("Map: ");

        // If map does not contain any value
        if (map.isEmpty()) {

            System.out.println("[]");
        }
        else {
            System.out.println(map);
        }
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {

        // Creating a Map
        // Declaring object of string and integer type
        Map<String, Integer> map = new HashMap<>();

        // Inserting elements in the Map object
        // using put() method
        // Custom input element addition
        map.put("ABC", 10);
        map.put("DEF", 30);
        map.put("XYZ", 20);

        // Calling method 2 to
        // print the map
        print(map);

        // Calling method 1 to
        // find the entry with highest value and
        // print on the console
        System.out.println(
            "Entry with highest value: "
            + getMaxEntryInMapBasedOnValue(map));
    }
}
```

**Output:** 

```
Map: {ABC=10, DEF=30, XYZ=20}
Entry with highest value: DEF=30
```

**方法 2:** 使用 Collections 类中不带 lambda 表达式的 max()方法

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Find Entry with largest Value in Map
// Using max() method from Collections class

// Importing required classes
import java.util.*;

// main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating HashMap
        // Declaring objects of string and integer type
        HashMap<Integer, Integer> map
            = new HashMap<Integer, Integer>();

        // Inserting elements in the Map
        // using put() method

        // Custom input addition
        map.put(1, 4);
        map.put(2, 5);
        map.put(3, 7);
        map.put(4, 2);

        // Using Collections.max() method returning max
        // value in HashMap and storing in a integer
        // variable
        int maxValueInMap = (Collections.max(map.values()));

        // Iterate through HashMap
        for (Entry<Integer, Integer> entry :
             map.entrySet()) {

            if (entry.getValue() == maxValueInMap) {

                // Print the key with max value
                System.out.println(entry.getKey());
            }
        }
    }
}
```

**输出:**

```
3
```

**方法 3:** 使用 Java 8 中引入的 Streams 概念

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Find Entry with largest Value in Map
// Using concept of Streams
import java.util.stream.*;

// Main class
class GFG {

    // Method 1
    public static void main(String[] args)
    {

        // Entries in our map
        Map<String, String> map = new HashMap<>();

        map.put("A", "23");
        map.put("F", "43");
        map.put("C", "56");
        map.put("Z", "04");

        // Printing the largest value in map by
        // calling above method
        System.out.print(map.maxUsingStreamAndLambda());
    }

    // Method 2
    public <String, String>
        extends Comparable<String> > maxUsingStreamAndLambda(
                    Map<String, String> map)
    {

        // Using lambda operation over streams
        Map<String, String> maxEntry
            = map.entrySet().stream().max(
                (String e1, String e2)
                    -> e1.getValue().compareTo(
                        0e2.getValue()));

        // Returning the maximum element from map
        return maxEntry.get().getValue();
    }
}
```

**输出:**

```
C
```