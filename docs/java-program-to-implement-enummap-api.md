# 实现枚举应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-enummap-api/](https://www.geeksforgeeks.org/java-program-to-implement-enummap-api/)

[枚举映射](https://www.geeksforgeeks.org/enummap-class-java-example/)是一个以枚举值为键的映射实现。现在，你们可能都想知道什么是 enum，对吧？嗯，enum 是用户定义的数据类型，通常在所有可能的值都已知时使用。

在本文中，我们将在一个 java 程序中实现 EnumMap API。但是首先，我们将学习一些在程序中使用过的概念，然后我们将直接进入程序。

EnumMap API 属于 [**java.util**](https://www.geeksforgeeks.org/java-util-package-java/) 包。为了实现 EnumMap 应用编程接口，将使用一个特殊的类，定义如下。

```java
EnumMapImpl<K extends Enum<K>, V> class
```

这个类表示枚举或枚举数据类型的枚举应用编程接口的使用。k 代表键类型条目，V 代表映射中的值类型条目。

**例 1:**

让我们考虑一个以服装尺寸为关键的 EnumMap。

```java
enum Dress_sizes
    {
        extra-small, small, medium, large, extra-large;
    }
```

现在，比方说，我们实现了 EnumMap API 的一个基本特性，我们想知道特定的服装尺寸是否可用，为此，我们将使用该函数。[**EnumMap . Contains Key(**](https://www.geeksforgeeks.org/enummap-containskey-method-in-java/#:~:text=util.,in%20this%20map%20or%20not.&text=Return%20Value%3A%20The%20method%20returns,EnumMap%20otherwise%20it%20returns%20false.)**)**，如果有大小，返回真，否则返回假。

**申报:**

```java
enumMap.containsKey(Dress_sizes.extra-large);

```

```java
Input: extra-large
Output: true

Input: extra-extra-large
Output: false
```

由于地图中存在超大尺寸，它返回真；由于不存在超大尺寸，它返回假。

**例 2:**

让我们再举一个这样的例子，实现 Map 的另一个基本特性，比如说我们想要清空上面的 EnumMap。为此，我们将简单地使用 [**enumMap.clear()**](https://www.geeksforgeeks.org/enummap-clear-method-in-java/) 函数来清除 enumMap。

**申报:**

```java
enumMap.clear();
```

```java
Output: The enumMap is now empty.       
        enum Dress_sizes
        { 

        }
```

**用于实施的方法:**

*   已经定义了一个枚举类，枚举值和键集是预定义的。
*   在主功能中，值已经与它们各自的键集配对。
*   然后使用基本的枚举函数来执行各种任务。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to implement enum Map API

import java.lang.*;
import java.util.Collection;
import java.util.EnumMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Set;

public class EnumMapImpl<K extends Enum<K>, V> {
    EnumMap<K, V> enumMap;

    // For creating an empty enum map with the specified key
    // type.
    public EnumMapImpl(Class<K> keyType)
    {
        enumMap = new EnumMap<K, V>(keyType);
    }

    // For creating an enum map which will have the same key
    // type as the specified enum map,

    public EnumMapImpl(EnumMap<K, ? extends V> m)
    {
        enumMap = new EnumMap<K, V>(m);
    }

    // For Creating an enum map that is initialized from the
    // specified map.
    public EnumMapImpl(Map<K, ? extends V> m)
    {
        enumMap = new EnumMap<K, V>(m);
    }

    // Clears the Mappings from the enumMap.
    public void clear() { enumMap.clear(); }

    // Returns true if the specified value is found.
    public boolean containsValue(Object value)
    {
        return enumMap.containsValue(value);
    }

    // Returns true if the specified key is found.
    public boolean containsKey(Object key)
    {
        return enumMap.containsKey(key);
    }

    // Returns the key set of the enumMap
    public Set<K> keySet() { return enumMap.keySet(); }

    // Returns the entry set( values + keys) of the enumMap.
    public Set<Map.Entry<K, V> > entrySet()
    {
        return enumMap.entrySet();
    }

    // Returns the value to which a specified key is mapped,
    // else returns null if the specified key is not found.

    public V get(Object key) { return enumMap.get(key); }

    // Associates the specified Key and Value.
    public V put(K key, V value)
    {
        return enumMap.put(key, value);
    }

    // Copies the mappings of another map to the specified
    // map.
    public void putAll(Map<? extends K, ? extends V> map)
    {
        enumMap.putAll(map);
    }

    // Returns the size of the enumMap.
    public int size() { return enumMap.size(); }

    // Returns the values mapped in the specified enumMap.
    public Collection<V> values()
    {
        return enumMap.values();
    }

    // Returns true if the enumMap is empty.
    public boolean isEmpty() { return enumMap.isEmpty(); }

    // Initializing the enumMap.
    enum Week_Days {
        SUNDAY,
        MONDAY,
        TUESDAY,
        WEDNESDAY,
        THURSDAY,
        FRIDAY,
        SATURDAY;
    }

    // Main function.
    public static void main(String[] args)
    {

        EnumMapImpl<Week_Days, Integer> enumMap
            = new EnumMapImpl<Week_Days, Integer>(Week_Days.class);

        enumMap.put(Week_Days.SUNDAY, 1);
        enumMap.put(Week_Days.MONDAY, 2);
        enumMap.put(Week_Days.TUESDAY, 3);
        enumMap.put(Week_Days.WEDNESDAY, 4);
        enumMap.put(Week_Days.THURSDAY, 5);
        enumMap.put(Week_Days.FRIDAY, 6);
        enumMap.put(Week_Days.SATURDAY, 7);

        System.out.println("The size of the enumMap is: "
                           + enumMap.size());

        System.out.println();

        System.out.println("The values of the enumMap is: ");

        Collection<Integer> ci = enumMap.values();

        Iterator<Integer> iin1 = ci.iterator();

        while (iin1.hasNext()) 
        {
            System.out.print(iin1.next() + "\t");
        }

        System.out.println();
        System.out.println();

        System.out.println("The key set of the enumMap is: ");

        Set<Week_Days> ws = enumMap.keySet();

        Iterator<Week_Days> iin2 = ws.iterator();

        while (iin2.hasNext()) 
        {
            System.out.print(iin2.next() + "  ");
        }

        System.out.println();
        System.out.println();

        System.out.println("The enumMap is: ");

        Iterator<Entry<Week_Days, Integer> > week_iterator;

        Set<Entry<Week_Days, Integer> > wi = enumMap.entrySet();
        week_iterator = wi.iterator();

        while (week_iterator.hasNext()) 
        {
            System.out.println(week_iterator.next() + "\t");
        }

        System.out.println();
        System.out.println("The enumMap contains Key SUNDAY "
            + ": " + enumMap.containsKey(Week_Days.SUNDAY));

        System.out.println("The enumMap contains Value 1 "
                           + ": "
                           + enumMap.containsValue(1));

        enumMap.clear();

        if (enumMap.isEmpty())
            System.out.println("The EnumMap is now empty.");
        else
            System.out.println("The EnumMap is not empty.");
    }
}
```

**Output**

```java
The size of the enumMap is: 7

The values of the enumMap is: 
1    2    3    4    5    6    7    

The key set of the enumMap is: 
SUNDAY  MONDAY  TUESDAY  WEDNESDAY  THURSDAY  FRIDAY  SATURDAY  

The enumMap is: 
SUNDAY=1    
MONDAY=2    
TUESDAY=3    
WEDNESDAY=4    
THURSDAY=5    
FRIDAY=6    
SATURDAY=7    

The enumMap contains Key SUNDAY : true
The enumMap contains Value 1 : true
The EnumMap is now empty.

```