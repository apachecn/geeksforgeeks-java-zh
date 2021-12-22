# Java 中的抽象映射

> 原文:[https://www.geeksforgeeks.org/abstractmap-in-java/](https://www.geeksforgeeks.org/abstractmap-in-java/)

抽象映射类是 T2 Java 收集框架的一部分。它直接实现了[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)接口，为其提供了一个结构，这样做使得进一步的实现更加容易。顾名思义，抽象映射是一个抽象类，因此不能用来创建对象。从抽象映射继承的具体类可以用来创建对象。

**申报:**

```
public abstract class AbstractMap<K,V> extends Object, implements Map<K,V>
```

这里 **K** 为键型， **V** 为值类型。

### 抽象地图的层次结构

![AbstractMap Hierarchy in Java](img/3f8d881c120436fdb427182ee716d981.png)

该类实现[映射< K，V >](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口，扩展[对象](https://www.geeksforgeeks.org/object-class-in-java/)类。

### 抽象映射的构造函数

<figure class="table">

| 

**施工方**

 | 

**定义**

 |
| --- | --- |
| 受保护的抽象映射() | 此构造函数不能用于创建对象。这个构造函数的存在是为了让继承类可以调用它，这个调用是隐式的。 |

</figure>

### 基本操作

**1。添加元素**

要向抽象地图添加元素，我们使用 [put()](https://www.geeksforgeeks.org/abstractmap-put-method-in-java-with-examples/) 方法。请注意，该方法实际上不是抽象映射类型，而是扩展类，对此对象的引用是抽象映射类型。映射的条目是类型键、值对。这里的键是整数类型的，值 id 是字符串类型的，这是在对象实例化时提到的。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate adding
// elements to the AbstractMap

import java.util.*;

public class AddElements {

    public static void main(String[] args)
    {
        // Since AbstractMap is an abstract class
        // create object using HashMap
        AbstractMap<Integer, String> absMap
            = new HashMap<Integer, String>();

        // Adding values to the AbstractMap
        // Note that we do not create an object of
        // AbstractMap
        absMap.put(1, "This");
        absMap.put(2, "is");
        absMap.put(3, "an");
        absMap.put(4, "AbstractMap");

        // Displaying the mappings using
        // entrySet() to get the set view
        System.out.println("The Set view of the mappings:");
        System.out.println(absMap.entrySet());
    }
}
```

**Output**

```
The Set view of the mappings:
[1=This, 2=is, 3=an, 4=AbstractMap]
```

**2。拆卸元件**

我们可以使用 [remove()](https://www.geeksforgeeks.org/abstractmap-remove-method-in-java-with-examples/) 方法从抽象映射中移除映射。remove 的语法是

```
mapName.remove(Object key);
```

这将删除映射到指定键的值。我们可以使用如下所示的 clear()方法清除整个抽象映射。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate removing
// elements from the AbstractMap

import java.util.*;

public class RemoveElements {

    public static void main(String[] args)
    {
        // Since AbstractMap is an abstract class
        // create object using HashMap
        AbstractMap<Integer, String> absMap
            = new HashMap<Integer, String>();

        absMap.put(1, "This");
        absMap.put(2, "is");
        absMap.put(3, "an");
        absMap.put(4, "AbstractMap");

        // Displaying the mappings
        System.out.println("Mappings of the AbstractMap:");
        System.out.println(absMap);

        // Removing an entry using the remove() method
        absMap.remove(1);

        // Displaying the mappings
        System.out.println("Mappings of the AbstractMap:");
        System.out.println(absMap);

        // Clearing the whole map using clear()
        absMap.clear();

        // Displaying the mappings
        System.out.println("\nThe Set view of the mappings:");
        System.out.println(absMap);
    }
}
```

**Output**

```
Mappings of the AbstractMap:
{1=This, 2=is, 3=an, 4=AbstractMap}
Mappings of the AbstractMap:
{2=is, 3=an, 4=AbstractMap}

The Set view of the mappings:
{}
```

**3。替换条目**

我们可以使用如下所示的 replace()方法替换与键相关联的值。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate replacing
// elements of AbstractMap

import java.util.AbstractMap;
import java.util.HashMap;

public class ReplaceElements {

    public static void main(String[] args)
    {

        // Since AbstractMap is an abstract class
        // create object using HashMap
        AbstractMap<Integer, String> absMap
            = new HashMap<Integer, String>();

        // Adding values to the AbstractMap
        // Note that we do not create an object of
        // AbstractMap
        absMap.put(1, "This");
        absMap.put(2, "is");
        absMap.put(3, "a");
        absMap.put(4, "AbstractMap");

        // Displaying the mappings
        System.out.println("Mappings of the AbstractMap:");
        System.out.println(absMap);

        // Replacing the mapping associated to 3
        absMap.replace(3, "an");

        // Displaying the mappings
        System.out.println("\nMappings of the AbstractMap:");
        System.out.println(absMap);
    }
}
```

**Output**

```
Mappings of the AbstractMap:
{1=This, 2=is, 3=a, 4=AbstractMap}

Mappings of the AbstractMap:
{1=This, 2=is, 3=an, 4=AbstractMap}
```

**4。穿越**

有不同的方法通过抽象地图遍历，我们在下面给出的代码中讨论两种方法。第一种方法是使用 [entrySet()](https://www.geeksforgeeks.org/hashmap-entryset-method-in-java/#:~:text=entrySet()%20method%20in%20Java%20is%20used%20to%20create%20a,the%20map%20elements%20into%20them.&text=Parameters%3A%20The%20method%20does%20not%20take%20any%20parameter.) 方法，返回地图的集合视图。对于每个循环，可以使用来迭代此视图。方法 **getKey()** 返回密钥， **getValue()** 返回关联值。第二种方法是使用迭代器接口。我们使用[键集()](https://www.geeksforgeeks.org/hashmap-keyset-method-in-java/)方法在键集上创建一个迭代器。此迭代器用于使用 next()方法迭代地图，该方法返回地图中的下一个条目。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate
// traversing AbstractMap

import java.util.*;

public class Traversing {

    public static void main(String[] args)
    {
        // Since AbstractMap is an abstract class
        // create object using HashMap
        AbstractMap<Integer, String> absMap
            = new HashMap<Integer, String>();

        // Adding values to the AbstractMap
        // Note that we do not create an object of
        // AbstractMap
        absMap.put(1, "This");
        absMap.put(2, "is");
        absMap.put(3, "a");
        absMap.put(4, "AbstractMap");

        // METHOD 1
        // Iterate over the map using entrySet()
        // which returns a collection view of the map

        System.out.println("Using the entrySet() method");

        for (AbstractMap.Entry<Integer, String> entry :
             absMap.entrySet()) {
            System.out.println("Key = " + entry.getKey()
                               + ", Value = "
                               + entry.getValue());
        }

        // METHOD 2
        // Iterate over the map using the Iterator interface

        System.out.println(
            "\nUsing the Iterator interface");

        Iterator<Integer> itr = absMap.keySet().iterator();
        while (itr.hasNext()) {
            int key = itr.next();
            System.out.println("Key = " + key
                               + ", Value =  "
                               + absMap.get(key));
        }
    }
}
```

**Output**

```
Using the entrySet() method
Key = 1, Value = This
Key = 2, Value = is
Key = 3, Value = a
Key = 4, Value = AbstractMap

Using the Iterator interface
Key = 1, Value =  This
Key = 2, Value =  is
Key = 3, Value =  a
Key = 4, Value =  AbstractMap
```

### 继承类

#### 1.HashMap

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java-with-examples/) 类是[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)接口的基本实现，存储键值对。散列表是散列表的基本映射实现，但是散列表是不同步的。哈希映射的元素顺序是未定义的。HashMap 为插入、删除、遍历和操作的基本操作提供了恒定的时间性能。

***语法:***

```
HashMap< ? , ? > hmName = new HashMap< ? , ? >();
```

#### 2.IdentityHashMap

[IdentityHashMap](https://www.geeksforgeeks.org/identityhashmap-class-java/) 是一个[映射](https://www.geeksforgeeks.org/map-interface-java-examples/)的 Hashtable 实现，但是它使用引用相等而不是对象相等。这意味着 IdentityHashMap 违反了地图的基本规则，因此它不是通用地图，它是为罕见场景保留的。在 IdentityHashMap 中，当且仅当 o1==o2，即 o1 和 o2 的引用相同时，任何两个对象 o1 和 o2 是相等的。

**语法:**

```
IdentityHashMap< ? , ? > ihmName = new IdentityHashMap< ? , ? >();
```

#### 3.WeakHashMap

[WeakHashMap](https://www.geeksforgeeks.org/java-util-weakhashmap-class-java/) 是使用弱键的 [Map](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口的哈希表实现。当武器地图中的一把钥匙不再被正常使用时，它将被自动丢弃。这意味着映射的存在不会阻止密钥被垃圾收集。WeakHashMap 是一个不同步的类。

**语法:**

```
WeakHashMap< ? , ? > whmName = new WeakHashMap< ? , ? >();
```

#### 4.树图

[树形图](https://www.geeksforgeeks.org/treemap-in-java/)类是一个基于红黑树的[导航图](https://www.geeksforgeeks.org/navigablemap-interface-in-java-with-example/#:~:text=NavigableMap%20is%20an%20extension%20of,than%20specified%20key%2C%20tailMap%20whose)的实现。树形图元素或者按照自然顺序排序，或者按照构建时提供的[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)排序。

**语法:**

```
TreeMap< ? , ? > tmName = new TreeMap< ? , ? >();
```

#### 5.枚举数

[枚举](https://www.geeksforgeeks.org/enummap-class-java-example/#:~:text=EnumMap%20class%20is%20a%20member,are%20declared%20inside%20enum%20type%20))是[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)界面的专门实现。枚举映射的键属于枚举类型。所有键都必须是在构造时指定的相同枚举，无论是显式定义还是隐式定义。EnumMap 在内部表示为一个数组，它非常紧凑和高效。

**语法:**

```
EnumMap< enumName, ? > emName = new EnumMap< enumName, ? >();
```

#### 6.ConcurrentHashMap

[ConcurrentHashMap](https://www.geeksforgeeks.org/concurrenthashmap-in-java/) 是一个 Hashtable 实现，通过检索和更新操作支持完全并发。这个类与哈希表类高度兼容，并且包含哈希表的所有对应方法。虽然这些操作是线程安全的，但是没有适当的锁定机制，因此检索可能会重叠更新。因此，检索操作反映了最近完成的更新操作。

**语法:**

```
ConcurrentHashMap< ? , ? > chmName = new ConcurrentHashMap< ? , ? >();
```

#### 7.concurrentskiplisstmap

[ConcurrentSkipListMap](https://www.geeksforgeeks.org/concurrentskiplistmap-ceilingkey-method-in-java-with-examples/#:~:text=concurrent.,when%20there%20is%20no%20key.) 是 ConcurrentNavigableMap 接口的可扩展实现。ConcurrentSkipListMap 中的键是按照自然顺序排序的，或者是在构建对象时使用[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)排序的。ConcurrentSkipListMap 的插入、删除和搜索操作的预期时间成本为 log n。它是一个线程安全的类，因此，所有的基本操作都可以同时完成。

**语法:**

```
ConcurrentSkipListMap< ? , ? > cslmName = new ConcurrentSkipListMap< ? , ? >();
```

### 抽象地图的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| [晴()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-clear-method-in-java-with-examples/&sa=U&ved=2ahUKEwjj9smlsq_sAhXnzzgGHbSLBusQFjAFegQIBRAC&usg=AOvVaw3wvGRZwaEjGalmO5dqRkFE) | 从此映射中移除所有映射(可选操作)。 |
| 克隆() | 返回这个抽象映射实例的一个浅拷贝:键和值本身没有被克隆。 |
| [包含键(对象键)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-containskey-method-in-java-with-examples/&sa=U&ved=2ahUKEwj_-bOEs6_sAhUJzTgGHddHDWY4ChAWMAZ6BAgDEAI&usg=AOvVaw3PTY3yOAJkCAAbIhXLvKuT) | 如果此映射包含指定键的映射，则返回 true。 |
| [包含值(对象值)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-containsvalue-method-in-java-with-examples/&sa=U&ved=2ahUKEwj_-bOEs6_sAhUJzTgGHddHDWY4ChAWMAJ6BAgIEAI&usg=AOvVaw31fSI_Y9dhn1Erk5z6GOy3) | 如果此映射将一个或多个键映射到指定值，则返回 true。 |
| [等于(对象 o)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-equals-method-in-java-with-examples/&sa=U&ved=2ahUKEwjj9smlsq_sAhXnzzgGHbSLBusQFjACegQICBAC&usg=AOvVaw0nLy9-sSveBL9IOQJfJ65E) | 将指定的对象与此映射进行比较，看是否相等。 |
| [获取(对象键)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-get-method-in-java-with-examples/&sa=U&ved=2ahUKEwjj9smlsq_sAhXnzzgGHbSLBusQFjABegQIBxAC&usg=AOvVaw2bboSUJ7tAAdrbQ7Y8wxcN) | 返回指定键映射到的值，如果此映射不包含键映射，则返回 null。 |
| [hashCode()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-hashcode-method-in-java-with-examples/&sa=U&ved=2ahUKEwjj9smlsq_sAhXnzzgGHbSLBusQFjAEegQIBhAC&usg=AOvVaw3wo3rTaJWi1DGw7DBI-cPj) | 返回此映射的哈希代码值。 |
| [【isempty()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-isempty-method-in-java-with-examples/&sa=U&ved=2ahUKEwjj9smlsq_sAhXnzzgGHbSLBusQFjAIegQIAxAC&usg=AOvVaw231KkSBdmBajM1bhKKYRbs) | 如果此映射不包含键值映射，则返回 true。 |
| [键集()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-keyset-method-in-java-with-examples/&sa=U&ved=2ahUKEwj_-bOEs6_sAhUJzTgGHddHDWY4ChAWMAB6BAgAEAI&usg=AOvVaw1dsQPyACvyNUlRLJ_bHsB2) | 返回此地图中包含的键的集合视图。 |
| [放(K 键，V 值)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-put-method-in-java-with-examples/&sa=U&ved=2ahUKEwjj9smlsq_sAhXnzzgGHbSLBusQFjAGegQIARAC&usg=AOvVaw3-iPxGAbNKy-bshDdxc0do) | 将指定值与此映射中的指定键相关联(可选操作)。 |
| [普塔尔(地图<？延伸 K，？延伸 V > m)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-putall-method-in-java-with-examples/&sa=U&ved=2ahUKEwjj9smlsq_sAhXnzzgGHbSLBusQFjADegQICRAC&usg=AOvVaw0ZjsGzWp_j1C1XhADkoiGn) | 将所有映射从指定映射复制到此映射(可选操作)。 |
| [移除(对象键)](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-remove-method-in-java-with-examples/&sa=U&ved=2ahUKEwjj9smlsq_sAhXnzzgGHbSLBusQFjAJegQIABAC&usg=AOvVaw1at6LI5GkFKopiaafAglqM) | 从该映射中删除键的映射(如果存在)(可选操作)。 |
| [尺寸()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-size-method-in-java-with-examples/&sa=U&ved=2ahUKEwjj9smlsq_sAhXnzzgGHbSLBusQFjAHegQIBBAC&usg=AOvVaw31XIWknREoO_wwif3eiJyK) | 返回此映射中键值映射的数量。 |
| toString() | 返回此映射的字符串表示形式。 |
| [值()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/abstractmap-values-method-in-java-with-examples/&sa=U&ved=2ahUKEwj_-bOEs6_sAhUJzTgGHddHDWY4ChAWMAN6BAgHEAI&usg=AOvVaw3UstcSBtlbT3uQXarAYGIZ) | 返回此地图中包含的值的集合视图。 |

</figure>

### 接口 java.util.Map 中声明的方法

<figure class="table">

| 

方法

 | 

描述

 |
| --- | --- |
| 计算(组合键，双功能 super K,​? super V,​? extends V>恢复功能) | 尝试计算指定键及其当前映射值的映射(如果没有当前映射，则为空)。 |
| 计算不存在(K 键，功能 super K,​? extends V>映射功能) | 如果指定的键尚未与值相关联(或映射为 null)，会尝试使用给定的映射函数计算其值，并将其输入到此映射中，除非为 null。 |
| 计算当前(K 键，双功能 super K,​? super V,​? extends V>恢复功能) | 如果指定键的值存在且不为空，将尝试计算给定键及其当前映射值的新映射。 |
| [输入 ySet()](https://www.geeksforgeeks.org/map-entryset-method-in-java-with-examples/) | 返回此映射中包含的映射的[集合](https://www.geeksforgeeks.org/set-in-java/)视图。 |
| forEach(双消费者〔t0〕行动) | 对此映射中的每个条目执行给定的操作，直到所有条目都已处理完毕或该操作引发异常。 |
| getOrDefault（Object key， V defaultValue） | 返回指定键映射到的值，如果此映射不包含键映射，则返回默认值。 |
| 合并(K 键，V 值，双功能 super V,​? super V,​? extends V>重映射功能) | 如果指定的键尚未与值相关联或与 null 相关联，则将其与给定的非 null 值相关联。 |
| 莆田(K key，V value) | 如果指定的键还没有与值相关联(或者被映射为 null)，则将它与给定值相关联并返回 null，否则返回当前值。 |
| 移除(对象键，对象值) | 仅当指定项当前映射到指定值时，才移除该项。 |
| 更换(K 键，V 值) | 仅当指定键当前映射到某个值时，才替换该项。 |
| 更换(K 键、旧值、新值) | 仅当当前映射到指定值时，替换指定键的条目。 |
| 替换全部(双功能 super K,​? super V,​? extends V>功能) | 将每个条目的值替换为对该条目调用给定函数的结果，直到所有条目都已处理完毕或函数引发异常。 |

</figure>