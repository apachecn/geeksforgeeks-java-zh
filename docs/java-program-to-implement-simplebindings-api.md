# 实现简单绑定应用编程接口的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-simplebindings-api/](https://www.geeksforgeeks.org/java-program-to-implement-simplebindings-api/)

SimpleBindings 是 HashMap 或程序员指定的任何其他映射所支持的绑定的实现。

**SimpleBindings API 的构造函数:**

*   SimpleBindings (): is the default constructor that uses HashMap to store values.
*   Simple binding (mapping m): Overloaded constructors use existing hash tables to store values.

**语法:**

```java
public class SimpleBindings extends Object implements Bindings
```

**实现 SimpleBindings API:**

## Java

```java
// Java Program to Implement SimpleBindings API

import java.util.Collection;
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Set;
import javax.script.SimpleBindings;

public class SimpleBindingsAPIExample {

    // reference of SimpleBindings class
    private SimpleBindings simpleBindings;

    // Default constructor will use a HashMap
    public SimpleBindingsAPIExample()
    {
        // object creating of SimpleBindings class
        simpleBindings = new SimpleBindings();
    }

    // Overloaded constructor uses an existing HashMap to
    // store the values
    public SimpleBindingsAPIExample(Map<String, Object> map)
    {
        simpleBindings = new SimpleBindings(map);
    }

    // Clear all the values from the map
    public void clear() { simpleBindings.clear(); }

    // Returns true if the map contains value for the
    // specified key
    public boolean containsKey(Object key)
    {
        return simpleBindings.containsKey(key);
    }

    // Return true if the map contains values as specified
    public boolean containsValue(Object value)
    {
        return simpleBindings.containsValue(value);
    }

    // Returns the set of values contained in the map
    public Set<Map.Entry<String, Object> > entrySet()
    {
        return simpleBindings.entrySet();
    }

    // Returns the values if specified key is exist in the
    // map else will return null
    public Object get(Object key)
    {
        return simpleBindings.get(key);
    }

    // Returns whether the map is empty or not
    public boolean isEmpty()
    {
        return simpleBindings.isEmpty();
    }

    // Returns a set of the keys
    public Set<String> keySet()
    {
        return simpleBindings.keySet();
    }

    // Insert the specified value associated with the
    // specified key
    public Object put(String key, Object value)
    {
        return simpleBindings.put(key, value);
    }

    // Copy all the values from another map into this map
    public void putAll(Map<? extends String, ? extends Object> map)
    {
        simpleBindings.putAll(map);
    }

    // Removes the value associated with the specified key
    public Object remove(Object key)
    {
        return simpleBindings.remove(key);
    }

    // Return the number of key-value pairs exist in the map
    public int size() { return simpleBindings.size(); }

    // Returns a collection of the values contained in map
    public Collection<Object> values()
    {
        return simpleBindings.values();
    }
}
class SimpleBindingsImpl {
    public static void main(String[] args)
    {
        SimpleBindingsAPIExample map = new SimpleBindingsAPIExample();

        map.put("1", "Ram");
        map.put("2", "Shyam");
        map.put("3", "Sita");

        Map<String, Object> anotherMap = new HashMap<String, Object>();

        anotherMap.put("4", "Geeta");
        anotherMap.put("5", "Tina");
        map.putAll(anotherMap);

        System.out.println("The key set of the map is : ");

        Set<String> keySet = map.keySet();
        Iterator<String> itr = keySet.iterator();

        while (itr.hasNext()) {
            System.out.print(itr.next() + "\n");
        }

        System.out.println();

        System.out.println("The values of map is :  ");

        Collection<Object> collectionOfValues = map.values();
        Iterator<Object> itrOfValues = collectionOfValues.iterator();

        while (itrOfValues.hasNext())
        {
            System.out.print(itrOfValues.next() + "\n");
        }
        System.out.println();

        System.out.println("The entry set of the map is ");
        Iterator<Entry<String, Object> > itrOfEntrySet;

        Set<Entry<String, Object> > entrySet = map.entrySet();
        itrOfEntrySet = entrySet.iterator();

        while (itrOfEntrySet.hasNext())
        {
            System.out.println(itrOfEntrySet.next());
        }
        System.out.println();

        // Returns true if map contains the key 2
        boolean check = map.containsKey("2");
        System.out.println("The map contains key 2 ? "
                           + check);
        System.out.println();

        // Return true if map contains the value snigdha
        check = map.containsValue("Tina");
        System.out.println("The map contains value Tina? "
                           + check);
        System.out.println();

        // Return the size of map
        int result = map.size();
        System.out.println("The number of key-value pairs in the map are : "
            + result);
        System.out.println();

        // Clear the map means delete all the key-value
        // pairs from the map
        map.clear();

        // Return true if map is empty
        check = map.isEmpty();
        System.out.println(
            "After clear the map, the map is empty ? "
            + check);
        System.out.println();
    }
}
```

**输出**

```java
The key set of the map is : 
1
2
3
4
5

The values of map is :  
Ram
Shyam
Sita
Geeta
Tina

The entry set of the map is 
1=Ram
2=Shyam
3=Sita
4=Geeta
5=Tina

The map contains key 2 ? true

The map contains value Tina? true

The number of key-value pairs in the map are : 5

After clear the map, the map is empty ? true
```