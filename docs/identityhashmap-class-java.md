# Java 中的 IdentityHashMap 类

> 原文:[https://www.geeksforgeeks.org/identityhashmap-class-java/](https://www.geeksforgeeks.org/identityhashmap-class-java/)

**标识哈希表**使用[哈希表](https://www.geeksforgeeks.org/hashtable-in-java/)实现[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)界面，在比较键(和值)时使用引用相等代替对象相等。此类不是通用的地图实现。虽然这个类实现了 Map 接口，但是它故意违反了 Map 的一般约定，该约定要求在比较对象时使用 equals()方法。当用户需要通过引用比较对象时，使用此类。属于 **java.util** 包。

**身份哈希映射的特征**

*   它遵循引用等式，而不是使用 equals()方法，而是使用==运算符。
*   它不是同步的，必须在外部同步。
*   迭代器是快速失效的，在迭代时抛出**ConcurrentModificationException**试图修改。
*   假设系统标识哈希函数(System.identityHashCode(Object))将元素适当地分散在存储桶中，这个类为基本操作(获取和放置)提供了恒定时间的性能。IdentityHashMap 不使用 hashCode()方法，而是使用 System.identityHashCode()方法。这是一个显著的区别，因为现在您可以在映射中使用可变对象作为键，当映射存储在 IdentityHashMap 中时，其哈希代码可能会改变。

**申报:**

> 公共类标识哈希映射<k>扩展抽象映射<k>实现映射<k>，可序列化，可克隆</k></k></k>

这里 **K** 为关键对象类型， **V** 为值对象类型。

**身份层次哈希表**

![IdentityHashMap in Java](img/02b4342b83cb5f83f2bca3dece05b469.png)

实现**可序列化**、**可克隆**、[映射< K、V>T5】接口，扩展**抽象映射< K、V>T7】类。**](https://www.geeksforgeeks.org/map-interface-java-examples/)

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate IdentityHashMap

import java.util.Map;
import java.util.HashMap;
import java.util.IdentityHashMap;

public class IdentityHashMapExample
{
    public static void main(String[] args)
    {
        // creating an instance of IdentityHashMap
        Map<String, String> ihm = new IdentityHashMap<>();

        // Putting key and value pair
        // in a IdentityHashMap Object
        ihm.put("ihmkey","ihmvalue");
        ihm.put(new String("ihmkey"),"ihmvalue1");

        // ihm.size() will print 2 since it
        // compares the objects by reference
        System.out.println("Size of IdentityHashMap--"+ihm.size());

    }
}
```

**Output**

```java
Size of IdentityHashMap--2
```

### IdentityHashMap 的构造函数

我们可以通过两种方式创建 **IdentityHashMap** 的实例:

```java
IdentityHashMap<K, V> ihm = new IdentityHashMap<K, V>();
            (or)
Map<K, V> hm = new IdentityHashMap<K, V>();
```

**1。IdentityHashMap():** 构造一个新的空身份哈希映射，默认预期最大大小。

> IdentityHashMap <k v="">他=新 identity hashmap<k v="">()；</k></k>

**2。IdentityHashMap(int expectedMaxSize):**使用指定的预期最大大小构建一个新的空映射。

> IdentityHashMap <k v="">他=新的 identityhashmap(int expectedmaxsize)；</k>

**3。IdentityHashMap(Map m):** 构建一个新的身份哈希映射，该映射包含指定映射中的键值映射。

> IdentityHashMap <k v="">他=新 identity hashmap(map m)；</k>

### 标识哈希映射的基本操作

**1。添加元素**

要将映射插入或添加到 IdentityHashMap 中，我们有 [put()](https://www.geeksforgeeks.org/identityhashmap-put-method-in-java/#:~:text=put()%20method%20of%20IdentityHashMap,replaced%20by%20the%20new%20value.) 和 [putAll()](https://www.geeksforgeeks.org/identityhashmap-putall-method-in-java/?ref=rp) 方法。put()可以将特定的键及其映射的值插入特定的映射中。如果传递了一个现有的键，那么前一个值将被新值替换。putAll()将所有元素(即映射)从一个映射复制到另一个映射。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate
// adding elements to IdentityHashMap
import java.util.*;

public class AddingElementsToIdentityHashMap {

    public static void main(String[] args)
    {
        // Creating an empty IdentityHashMap
        Map<Integer, String> identity_hash
            = new IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        // using put() method
        identity_hash.put(10, "Geeks");
        identity_hash.put(15, "4");
        identity_hash.put(20, "Geeks");
        identity_hash.put(25, "Welcomes");
        identity_hash.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: "
                           + identity_hash);

        // Inserting existing key along with new value
          // previous value gets returned and stored in
          // returned_value
        String returned_value
            = (String)identity_hash.put(20, "All");

        // Verifying the returned value
        System.out.println("Returned value is: "
                           + returned_value);

        // Displaying the new map
        System.out.println("New map is: " + identity_hash);

        // Creating a new Identityhash map and copying
        Map<Integer, String> new_Identityhash_map
            = new IdentityHashMap<Integer, String>();
        new_Identityhash_map.putAll(identity_hash);

        // Displaying the final IdentityHashMap
        System.out.println("The new map: "
                           + new_Identityhash_map);
    }
}
```

**Output**

```java
Initial Mappings are: {10=Geeks, 25=Welcomes, 30=You, 20=Geeks, 15=4}
Returned value is: Geeks
New map is: {10=Geeks, 25=Welcomes, 30=You, 20=All, 15=4}
The new map: {10=Geeks, 25=Welcomes, 30=You, 20=All, 15=4}
```

**2。移除元素**
要移除映射，我们使用[移除()](https://www.geeksforgeeks.org/identityhashmap-remove-method-in-java/)，一种内置的 IdentityHashMap 类方法，用于从映射中移除任何特定键的映射。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to illustrate removing
// elements from IdentityHashMap

import java.util.*;

public class RemovingMappingsFromIdentityHashMap {
    public static void main(String[] args)
    {

        // Creating an empty IdentityHashMap
        Map<Integer, String> Identity_hash = new
                    IdentityHashMap<Integer, String>();

        // Mapping string values to int keys
        Identity_hash.put(10, "Geeks");
        Identity_hash.put(15, "4");
        Identity_hash.put(20, "Geeks");
        Identity_hash.put(25, "Welcomes");
        Identity_hash.put(30, "You");

        // Displaying the IdentityHashMap
        System.out.println("Initial Mappings are: " +
                                        Identity_hash);

        // Removing the existing key mapping
        String returned_value =
                        (String)Identity_hash.remove(20);

        // Verifying the returned value
        System.out.println("Returned value is: " +
                                    returned_value);

        // Displaying the new map
        System.out.println("New map is: " + Identity_hash);
    }
}
```

**Output**

```java
Initial Mappings are: {10=Geeks, 25=Welcomes, 30=You, 20=Geeks, 15=4}
Returned value is: Geeks
New map is: {10=Geeks, 25=Welcomes, 30=You, 15=4}
```