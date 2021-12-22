# 如何在树形图中替换给定键的值？

> 原文:[https://www . geesforgeks . org/如何用给定的树中键替换值图/](https://www.geeksforgeeks.org/how-to-replace-a-value-for-the-given-key-in-the-treemap/)

Java 中的 [树形图](https://www.geeksforgeeks.org/treemap-in-java/) 与抽象地图类一起用于实现 [地图界面](https://www.geeksforgeeks.org/map-interface-java-examples/) 和 [导航地图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/) 。地图根据其键的自然顺序进行排序，或者通过地图创建时提供的 [比较器](https://www.geeksforgeeks.org/comparator-interface-java/) 进行排序，具体取决于使用的构造函数。

*   它是 Map 接口的实现类。
*   它根据键对元素进行排序。
*   它不维护插入顺序。

**用给定的键替换数值的方法:**

1.  使用 TreeMap 类的 put()方法
2.  使用 TreeMap 类的 replace()方法
3.  使用 TreeMap 类的 ComputeIfPresent()方法

**1。** [**放()法**](https://www.geeksforgeeks.org/treemap-put-method-in-java/) **:**

**语法:**

```java
Tree_Map.put(*key, value*)
```

**参数:**该方法采用两个参数，都是树形图的对象类型。

*   *关键:*这是指需要插入到 Map 中进行映射的关键元素。
*   *值:*这是指上述键将映射到的值。

**返回值:**如果传递了一个现有的键，则返回前一个值。如果传递了新的对，则返回空值。

*   使用 put 方法，我们可以替换已经存在的键值，但是如果键值不存在，它会创建一个新记录。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program  to replace a value for 
// the given key in the TreeMap

import java.io.*;
import java.util.TreeMap;
class GFG {
    public static void main (String[] args) {

      TreeMap<String,Integer> gfg=new TreeMap<>();

      //adding values to the treemap

      gfg.put("dsa",99);
      gfg.put("interview",98);
      gfg.put("fang",80);

      //for the fang key we will change the value from 80 to 99
      //using put method
      gfg.put("fang",99);

      for(String key: gfg.keySet()){
      System.out.println(key+" , "+gfg.get(key));
      }
    }
}
```

**Output**

```java
dsa , 99
fang , 99
interview , 98
```

**2。使用** [**替换()**](https://www.geeksforgeeks.org/hashmap-replacekey-value-method-in-java-with-examples/) **方法:**

*   replace()方法替换给定键的值，但是 replace 和 put 之间有区别。
*   在替换的情况下，如果密钥不存在，它不会创建新的记录。

**语法:**

```java
public V replace(K key, V value)
```

**参数:**该方法接受两个参数:

*   **键:**是要替换其值的元素的键。
*   **值:**是必须用提供的键映射的新值。

**返回值:**该方法返回与指定键关联的**上一个值**。如果没有映射这样的键，那么如果实现支持空值，则返回**空值**。

**例外:** 此法会投:

*   [**空指针异常**](https://www.geeksforgeeks.org/null-pointer-exception-in-java/) 如果指定的键或值为空，并且此映射不允许空键或值，并且
*   **IllegalArgumentException** 如果指定键或值的某些属性阻止其存储在该映射中。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program  to replace a value 
// for the given key in the TreeMap

import java.io.*;
import java.util.TreeMap;
class GFG {
    public static void main (String[] args) {

      TreeMap<String,Integer> gfg=new TreeMap<>();

      //adding values to the treemap

      gfg.put("dsa",99);
      gfg.put("interview",98);
      gfg.put("fang",80);

      //here we are using dsa key to change its value form 99 to 100
      gfg.replace("dsa",100);

      for(String key: gfg.keySet()){
      System.out.println(key+" , "+gfg.get(key));
      }
    }
}
```

**Output**

```java
dsa , 100
fang , 80
interview , 98
```

**3。**[**computeIfPresent()**](https://www.geeksforgeeks.org/hashmap-computeifpresentkey-bifunction-method-in-java-with-examples/)**方法:**

*   它存在于 java 8 中。HashMap 类的 **computeIfPresent(Key，BiFunction)** 方法，如果某个键已经与某个值相关联(或者映射为空)，该方法允许您计算指定键的映射值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program  to replace a value 
// for the given key in the TreeMap

import java.io.*;
import java.util.TreeMap;
class GFG {
    public static void main (String[] args) {

      TreeMap<String,Integer> gfg=new TreeMap<>();

      //adding values to the treemap

      gfg.put("dsa",99);
      gfg.put("interview",98);
      gfg.put("fang",80);

      //here we are using interview key to change its value form 98 to 50
      gfg.computeIfPresent("interview",(k,v)->50);

      for(String key: gfg.keySet()){
      System.out.println(key+" , "+gfg.get(key));
      }
    }
}
```

**Output**

```java
dsa , 99
fang , 80
interview , 50
```