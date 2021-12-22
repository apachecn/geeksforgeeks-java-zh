# Java 中的地图界面

> 原文:[https://www.geeksforgeeks.org/map-interface-java-examples/](https://www.geeksforgeeks.org/map-interface-java-examples/)

映射接口存在于 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中，表示键和值之间的映射。地图界面不是[采集界面](https://www.geeksforgeeks.org/collections-in-java-2/)的子类型。因此，它的行为与其他集合类型有些不同。地图包含唯一的键。

极客们，头脑风暴者应该是为什么和什么时候使用地图？

映射非常适合用于键值关联映射，例如字典。映射用于按键执行查找，或者当有人想要按键检索和更新元素时。一些常见的场景如下:

*   错误代码及其描述的映射。
*   邮政编码和城市地图。
*   经理和员工的地图。每个经理(关键)都与他管理的员工(价值)列表相关联。
*   班级和学生的地图。每个类(键)都与一个学生列表(值)相关联。

**创建地图对象**

由于地图是一个[界面](https://www.geeksforgeeks.org/interfaces-in-java/)，因此不能创建地图类型的对象。为了创建一个对象，我们总是需要一个扩展这个映射的类。此外，在 Java 1.5 中引入[泛型](https://www.geeksforgeeks.org/generics-in-java/)后，可以限制地图中可以存储的对象类型。

**语法:**定义类型安全映射

```
Map hm = new HashMap(); 
// Obj is the type of the object to be stored in Map
```

**地图界面的特征**

1.  映射不能包含重复的键，每个键最多只能映射到一个值。有些实现允许空键和空值，如[哈希表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)和[链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)，但有些不喜欢[树状图](https://www.geeksforgeeks.org/treemap-in-java/)。
2.  地图的顺序取决于具体的实现。例如[树形图](https://www.geeksforgeeks.org/treemap-in-java/)和[链接的 HashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 有可预测的订单，而 [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 没有。
3.  在 java 中实现 Map 有两个接口。它们是 Map 和 [SortedMap](https://www.geeksforgeeks.org/sortedmap-java-examples/) ，以及三个类:HashMap、TreeMap 和 LinkedHashMap。

### 地图界面中的方法

<figure class="table">

| 方法 | 已执行的操作 |
| --- | --- |
| [晴()](https://www.geeksforgeeks.org/map-clear-method-in-java-with-example/) | 此方法用于清除和移除指定地图集合中的所有元素或映射。 |
| [包含键(对象)](https://www.geeksforgeeks.org/map-containskey-method-in-java-with-examples/) | 此方法用于检查特定键是否映射到映射中。它将关键元素作为参数，如果该元素在映射中被映射，则返回 True。 |
| [包含值(对象)](https://www.geeksforgeeks.org/map-containsvalue-method-in-java-with-examples/) | 此方法用于检查特定值是由映射中的单个键映射还是由多个键映射。它将该值作为参数，如果该值由映射中的任何键映射，则返回 True。 |
| [输入 ySet()](https://www.geeksforgeeks.org/map-entryset-method-in-java-with-examples/) | 此方法用于创建地图中包含的相同元素的集合。它基本上返回地图的集合视图，或者我们可以创建一个新的集合并将地图元素存储到其中。 |
| [等于(对象)](https://www.geeksforgeeks.org/map-equals-method-in-java-with-examples/) | 此方法用于检查两个地图之间的相等性。它验证作为参数传递的一个映射的元素是否等于这个映射的元素。 |
| [获取(对象)](https://www.geeksforgeeks.org/map-get-method-in-java-with-examples/) | 此方法用于检索或获取由参数中提到的特定键映射的值。当映射不包含键的这种映射时，它返回空值。 |
| [hashCode()](https://www.geeksforgeeks.org/map-hashcode-method-in-java-with-examples/) | 此方法用于为包含键和值的给定映射生成哈希代码。 |
| [【isempty()](https://www.geeksforgeeks.org/map-isempty-method-in-java-with-examples/) | 此方法用于检查映射是否有任何键和值对的条目。如果不存在映射，则返回 true。 |
| [键集()](https://www.geeksforgeeks.org/map-keyset-method-in-java-with-examples/) | 此方法用于返回此地图中包含的键的集合视图。集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。 |
| [put(Object，Object)](https://www.geeksforgeeks.org/map-put-method-in-java-with-examples/) | 此方法用于将指定值与此映射中的指定键相关联。 |
| putall(地图) | 此方法用于将指定映射中的所有映射复制到此映射。 |
| [移除(对象)](https://www.geeksforgeeks.org/map-remove-method-in-java-with-examples/) | 如果某个键存在于地图中，则此方法用于从此地图中移除该键的映射。 |
| 大小() | 此方法用于返回映射中可用的键/值对的数量。 |
| 值() | 此方法用于根据地图的值创建集合。它基本上返回哈希表中值的集合视图。 |
| getOrDefault（Object key， V defaultValue） | 返回指定键映射到的值，如果此映射不包含键映射，则返回默认值。 |
| 合并(K 键，V 值，双功能 super V,? super V,? extends V>重映射功能) | 如果指定的键尚未与值相关联或与 null 相关联，则将其与给定的非 null 值相关联。 |
| 莆田(K key，V value) | 如果指定的键还没有与值相关联(或者映射为 null)，则将它与给定的值相关联并返回 null，否则返回 curassociaterent 值。 |

</figure>

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Demonstrate
// Working of Map interface

// Importing required classes
import java.util.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[])
    {
        // Creating an empty HashMap
        Map<String, Integer> hm
            = new HashMap<String, Integer>();

        // Inserting pairs in above Map
        // using put() method
        hm.put("a", new Integer(100));
        hm.put("b", new Integer(200));
        hm.put("c", new Integer(300));
        hm.put("d", new Integer(400));

        // Traversing through Map using for-each loop
        for (Map.Entry<String, Integer> me :
             hm.entrySet()) {

            // Printing keys
            System.out.print(me.getKey() + ":");
            System.out.println(me.getValue());
        }
    }
}
```

**Output:** 

```
a:100
b:200
c:300
d:400
```

实现映射接口的类在下面的媒体中描述，后面将描述如下:

![](img/bcb5be4b7476c8d0b485262d031fc896.png)

**1 级:** [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)

自 Java 1.2 以来，HashMap 就是 Java 集合的一部分。它提供了 Java 的 Map 接口的基本实现。它以(键、值)对的形式存储数据。要访问一个值，必须知道它的键。这个类使用一种叫做[散列](https://www.geeksforgeeks.org/hashing-data-structure/)的技术。哈希是一种将大字符串转换为代表相同字符串的小字符串的技术。较短的值有助于索引和更快的搜索。让我们看看如何使用这个类创建一个地图对象。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate the Hashmap Class

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty HashMap
        Map<String, Integer> map = new HashMap<>();

        // Inserting entries in the Map
        // using put() method
        map.put("vishal", 10);
        map.put("sachin", 30);
        map.put("vaibhav", 20);

        // Iterating over Map
        for (Map.Entry<String, Integer> e : map.entrySet())

            // Printing key-value pairs
            System.out.println(e.getKey() + " "
                               + e.getValue());
    }
}
```

**Output:** 

```
vaibhav 20
vishal 10
sachin 30
```

**2 级:** [链接哈希表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)

LinkedHashMap 就像 HashMap 一样，有一个额外的特性，即维护插入其中的元素的顺序。HashMap 提供了快速插入、搜索和删除的优势，但是它从来没有维护过 LinkedHashMap 提供的插入的轨迹和顺序，在那里元素可以按照它们的插入顺序被访问。让我们看看如何使用这个类创建一个地图对象。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate the LinkedHashmap Class

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty LinkedHashMap
        Map<String, Integer> map = new LinkedHashMap<>();

        // Inserting pair entries in above Map
        // using put() method
        map.put("vishal", 10);
        map.put("sachin", 30);
        map.put("vaibhav", 20);

        // Iterating over Map
        for (Map.Entry<String, Integer> e : map.entrySet())

            // Printing ket-value pairs
            System.out.println(e.getKey() + " "
                               + e.getValue());
    }
}
```

**Output:** 

```
vishal 10
sachin 30
vaibhav 20
```

**3 级:** [**树形图**](https://www.geeksforgeeks.org/treemap-in-java/)

Java 中的树形图与抽象类一起用于实现地图接口和导航地图。地图根据其关键字的自然顺序进行排序，或者由地图创建时提供的比较器进行排序，具体取决于使用的构造函数。这被证明是排序和存储键值对的有效方式。树图维护的存储顺序必须和其他排序图一样与 equals 一致，而不考虑显式比较器。让我们看看如何使用这个类创建一个地图对象。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Illustrate TreeMap Class

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty TreeMap
        Map<String, Integer> map = new TreeMap<>();

        // Inserting custom elements in the Map
        // using put() method
        map.put("vishal", 10);
        map.put("sachin", 30);
        map.put("vaibhav", 20);

        // Iterating over Map using for each loop
        for (Map.Entry<String, Integer> e : map.entrySet())

            // Printing key-value pairs
            System.out.println(e.getKey() + " "
                               + e.getValue());
    }
}
```

**Output:** 

```
sachin 30
vaibhav 20
vishal 10
```

### 使用*地图界面*和 *HashMap 类*执行各种操作

因为 Map 是一个接口，所以它只能与实现该接口的类一起使用。现在，让我们看看如何使用广泛使用的 [HashMap 类](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/)在地图上执行一些常用的操作。此外，在 Java 1.5 中引入[泛型](https://www.geeksforgeeks.org/generics-in-java/)后，可以限制地图中可以存储的对象类型。

**操作 1:** 添加元素

为了给地图增加一个元素，我们可以使用 [put()方法](https://www.geeksforgeeks.org/map-put-method-in-java-with-examples/)。但是，插入顺序不会保留在 hashmap 中。在内部，对于每个元素，都会生成一个单独的哈希，并基于该哈希对元素进行索引，以提高效率。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the working of Map interface

import java.util.*;
class GFG {
    public static void main(String args[])
    {
        // Default Initialization of a
        // Map
        Map<Integer, String> hm1 = new HashMap<>();

        // Initialization of a Map
        // using Generics
        Map<Integer, String> hm2
            = new HashMap<Integer, String>();

        // Inserting the Elements
        hm1.put(1, "Geeks");
        hm1.put(2, "For");
        hm1.put(3, "Geeks");

        hm2.put(new Integer(1), "Geeks");
        hm2.put(new Integer(2), "For");
        hm2.put(new Integer(3), "Geeks");

        System.out.println(hm1);
        System.out.println(hm2);
    }
}
```

**Output:** 

```
{1=Geeks, 2=For, 3=Geeks}
{1=Geeks, 2=For, 3=Geeks}
```

**操作 2:** 改变元素

添加元素后，如果我们想改变元素，可以通过 [put()方法再次添加元素来完成。](https://www.geeksforgeeks.org/hashmap-put-method-in-java/)由于地图中的元素是使用关键字索引的，因此可以通过简单地插入我们希望更改的关键字的更新值来更改关键字的值。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// the working of Map interface

import java.util.*;
class GFG {
    public static void main(String args[])
    {

        // Initialization of a Map
        // using Generics
        Map<Integer, String> hm1
            = new HashMap<Integer, String>();

        // Inserting the Elements
        hm1.put(new Integer(1), "Geeks");
        hm1.put(new Integer(2), "Geeks");
        hm1.put(new Integer(3), "Geeks");

        System.out.println("Initial Map " + hm1);

        hm1.put(new Integer(2), "For");

        System.out.println("Updated Map " + hm1);
    }
}
```

**Output:** 

```
Initial Map {1=Geeks, 2=Geeks, 3=Geeks}
Updated Map {1=Geeks, 2=For, 3=Geeks}
```