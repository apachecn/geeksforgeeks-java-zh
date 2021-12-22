# Java 树形图特殊方法

> 原文:[https://www.geeksforgeeks.org/java-treemap-special-methods/](https://www.geeksforgeeks.org/java-treemap-special-methods/)

Java 中的[树形图](https://www.geeksforgeeks.org/treemap-in-java/)与[抽象地图类](https://www.geeksforgeeks.org/abstractmap-in-java/)一起实现地图接口和[导航地图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/)。地图根据其关键字的自然顺序进行排序，或者由地图创建时提供的比较器进行排序，具体取决于使用的构造函数。由于导航地图接口和排序数据的实现，TreeMap 提供了某些特殊的功能，这些功能在任何其他地图实现中都不存在。

**方法 1:** *firstKey()*

它返回当前地图中的第一个(最低的)键。

**语法:**

```
public K firstKey()
```

**返回值:**当前在此地图中的第一个(最低的)键。

> **注意:**如果该地图为空，则引发 NoSuchElementException。

**示例:**

## Java

```
//  Java Program to illustrate firstKey() method of TreeMap

// Importing input output classes
import java.io.*;
// Importing treeMap class from java.util package
import java.util.TreeMap;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of TreeMap of type Character
        // and String
        TreeMap<Character, Integer> treeMap
            = new TreeMap<>();

        // Inserting elements to the object created above

        // Custom entries
        treeMap.put('A', 1);
        treeMap.put('F', 5);
        treeMap.put('M', 2);
        treeMap.put('K', 9);
        treeMap.put('G', 4);
        treeMap.put('J', 7);

        // Display all the elements in the object of TreeMap
        System.out.println("Tree Map : " + treeMap);

        // Print and display the lowest key
        // using firstkey() method
        System.out.println("Lowest Key is : "
                           + treeMap.firstKey());
    }
}
```

**输出**

```
Tree Map : {A=1, F=5, G=4, J=7, K=9, M=2}
Lowest Key is : A
```

**方法二:**[*【last key()*](https://www.geeksforgeeks.org/treemap-lastkey-method-in-java/)

java.util.TreeMap.lastKey()用于检索地图中最后或最高的键。

**语法:**

```
tree_map.lastKey();
```

**返回值:**该方法返回地图中出现的最后一个键。

**异常:**如果地图为空，该方法抛出*nosucheelementexception*。

**示例:**

## Java

```
// Java Program to illustrate lastKey() Method in TreeMap

// Importing input output classes
import java.io.*;
// Importing TreeMap class from java.util package
import java.util.TreeMap;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of TreeMap of type Character
        // and Integer
        TreeMap<Character, Integer> treeMap
            = new TreeMap<>();

        // Adding elements to the object created above
        // Custom entries
        treeMap.put('A', 1);
        treeMap.put('F', 5);
        treeMap.put('M', 2);
        treeMap.put('K', 9);
        treeMap.put('G', 4);
        treeMap.put('J', 7);

        // Print and display all the elements in the TreeMap
        System.out.println("Tree Map : " + treeMap);

        // Print the highest key in the TreeMap
        // using lastKey() method
        System.out.println("Highest Key is : "
                           + treeMap.lastKey());
    }
}
```

**输出**

```
Tree Map : {A=1, F=5, G=4, J=7, K=9, M=2}
Highest Key is : M
```

**方法三:** [*头帽(Object key_value)*](https://www.geeksforgeeks.org/treemap-headmap-method-in-java/)

TreeMap 类的 Java . util . tree map . hear map(*key _ point*)方法用于获取严格小于参数 key_value 的所有对或部分映射。上述参数不包括在新准备的树形图中。由于集合由地图支持，因此对地图的任何更改都会反映在其他地图中，反之亦然。

**语法:**

```
sorted_map = old_treemap.headMap(*key_point*)
```

**参数:**该方法取树形图中取的键类型的一个参数 *key_point* ，并引用该点，直到返回键值对。

**返回值:**该方法返回树图中键严格小于 key_point 的部分。

**异常:**该方法抛出三种类型的异常:

*   [T0】 class castexception: 【T1] This exception is thrown when the key_point is incompatible or incomparable with the maps comparator.
*   [T0】 NullPointRexception: 【T1] This exception is thrown when the key point is empty.
*   *IllegalException:* This exception will be thrown when the key_point is out of range or beyond the map range limit.

**例:**

## 爪哇

```
// Java Program to illustrate headMap() method of TreeMap

// Importing input output classes
import java.io.*;
// Importing TreeMap class from java.util package
import java.util.TreeMap;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an object of TreeMap of character and
        // Integer type
        TreeMap<Character, Integer> treeMap
            = new TreeMap<>();

        // Adding elements to the object of TreeMap
        // Custom entries
        treeMap.put('A', 1);
        treeMap.put('F', 5);
        treeMap.put('M', 2);
        treeMap.put('K', 9);
        treeMap.put('G', 4);
        treeMap.put('J', 7);

        // Prin and display all elements in the object
        System.out.println("Tree Map : " + treeMap);

        // Print elements inclusive of key value passed
        // using headMap() method
        System.out.println(
            "Head Map exclusive of the key value : "
            + treeMap.headMap('G'));

        // Similarly to include the value passed
        // We can add a boolean argument as
        System.out.println(
            "Head Map inclusive of the key value : "
            + treeMap.headMap('G', true));
    }
}
```

**输出**

```
Tree Map : {A=1, F=5, G=4, J=7, K=9, M=2}
Head Map exclusive of the key value : {A=1, F=5}
Head Map inclusive of the key value : {A=1, F=5, G=4}
```