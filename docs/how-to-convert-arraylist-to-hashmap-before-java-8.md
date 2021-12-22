# 【Java 8 之前如何将 ArrayList 转换成 HashMap？

> 原文:[https://www . geesforgeks . org/how-convert-ArrayList-to-hashmap-before-Java-8/](https://www.geeksforgeeks.org/how-to-convert-arraylist-to-hashmap-before-java-8/)

ArrayList 是一个可调整大小的数组。它在 java 包 java.util 下，用 java 给出动态数组。数组列表在需要对数组进行大量更改的程序中非常有用，但这些更改也比标准数组慢。数组列表中的元素可以随时添加和删除。

HashMap 是一种以“键/值”对存储项目的数据结构。它们可以由另一种类型的索引访问，如字符串。散列表被表示为散列表<key value="">。这与哈希表非常相似，但是它允许使用空值和空键。它不会按照键和值存储到哈希表中的相同顺序返回它们。它也在 java 包 java.util 下。</key>

现在，为了将[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)转换为[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)，这两个用例也被认为是为了说明覆盖概念

1.  初始数组列表没有重复项
2.  初始数组列表有重复值。

**案例 1:** 在 Java 8 之前将数组列表转换为 HashMap 的最理想的方法是通过使用增强的 for-loop 迭代给定的数组列表，并将 String 作为键，将其长度作为值插入 HashMap。在这里，数组列表的每个元素都可以转换成一个键值对，并存储在 HashMap 中。此方法还处理数组列表中的任何重复项，因为在重复键的情况下，插入的条目会覆盖值。在这种情况下，不会引发错误或异常。

**示例:**初始数组列表没有重复

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to convert ArrayList
// to Hashmap before Java 8

// Name of ArrayList chosen randomly: vehicleList

// Importing java generic libraries
import java.util.*;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating ArrayList
        ArrayList<String> vehicleList
            = new ArrayList<>(Arrays.asList(
                "Car", "Bike", "Bus", "Cycle", "Rickshaw"));

        // Display message to enter ArrayList
        System.out.println("ArrayList: \n");

        // Printing ArrayList
        for (String vehicle : vehicleList) {
            System.out.println(vehicle);
        }

        // Display message to separate above
        // list from hashmap for readability
        System.out.println("\nHashMap: \n");

        // Creating Hashmap
        HashMap<String, Integer> vehicleMap
            = convertArrayListToHashMap(vehicleList);

        for (Map.Entry<String, Integer> entry :
             vehicleMap.entrySet()) {
            System.out.println(entry.getKey() + " : "
                               + entry.getValue());
        }
    }

    // Converting ArrayList to HashMap
    private static HashMap<String, Integer>
    convertArrayListToHashMap(ArrayList<String> arrayList)
    {
        HashMap<String, Integer> hashMap = new HashMap<>();

        // For-each loop for iteration
        for (String str : arrayList) {
            hashMap.put(str, str.length());
        }

        // Returning converted Hashmap
        return hashMap;
    }
}
```

**Output**

```
ArrayList: 

Car
Bike
Bus
Cycle
Rickshaw

HashMap: 

Bus : 3
Rickshaw : 8
Car : 3
Bike : 4
Cycle : 5
```

**情况 2:** 初始数组列表有重复的值，由于哈希映射中有重复的键，它覆盖了该值。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Program to convert ArrayList
// to Hashmap before Java 8

// Importing java generic libraries
import java.util.*;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating ArrayList
        ArrayList<String> vehicleList = new ArrayList<>(

            // Presence of Duplicate Elements
            Arrays.asList("Car", "Bike", "Bus", "Cycle",
                          "Rickshaw", "Car", "Bike"));

        System.out.println("ArrayList: \n");

        // Printing ArrayList
        for (String vehicle : vehicleList) {
            System.out.println(vehicle);
        }

        // Display message just after ArratList is printed
        // for better readability
        System.out.println("\nHashMap: \n");

        // Creating HashMap
        HashMap<String, Integer> vehicleMap
            = convertArrayListToHashMap(vehicleList);

        // Printing above HashMap
        for (Map.Entry<String, Integer> entry :
             vehicleMap.entrySet()) {
            System.out.println(entry.getKey() + " : "
                               + entry.getValue());
        }
    }

    // Converting ArrayList to HashMap
    private static HashMap<String, Integer>
    convertArrayListToHashMap(ArrayList<String> arrayList)
    {
        HashMap<String, Integer> hashMap = new HashMap<>();

        // For-each loop for iteration
        for (String str : arrayList) {
            hashMap.put(str, str.length());
        }

        // Returning converted HashMap
        return hashMap;
    }
}
```

**Output**

```
ArrayList: 

Car
Bike
Bus
Cycle
Rickshaw
Car
Bike

HashMap: 

Bus : 3
Rickshaw : 8
Car : 3
Bike : 4
Cycle : 5
```