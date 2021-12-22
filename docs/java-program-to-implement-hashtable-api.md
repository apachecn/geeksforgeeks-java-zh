# 实现哈希表 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-hashtable-api/](https://www.geeksforgeeks.org/java-program-to-implement-hashtable-api/)

[**哈希表**](https://www.geeksforgeeks.org/hashtable-in-java/) 类实现了一个哈希表，将键映射到值。任何非空对象都可以用作键或值。为了成功地从哈希表中存储和检索对象，用作键的对象必须实现 hashCode 方法和 equals 方法。

为了**实现** Hashtable API 首先，我们创建一个类“Hashtable”，并在这个类中创建 Hashtable 的所有方法:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to implement the hashTable API

import java.util.*;
import java.util.Map.Entry;

class HashTableImplementation<K, V>
{
    private Hashtable<K, V> hashTable;

    // Constructor creates a new HashTable 
    public HashTableImplementation()
    {
        hashTable = new Hashtable<K, V>();
    }

    // Constructor creates a new empty Hashtable 
    // according to the given Hashtable
    public HashTableImplementation(Map<? extends K, ? extends V> hashTable1)
    {
        hashTable = new Hashtable<K, V>(hashTable1);
    }

    // Removes all of the elements from the hashTable
    public void clear()
    {
        hashTable.clear();
    }

    // Creates a shallow copy of the hashtable
    public Object clone()
    {
        return hashTable.clone();
    }

    // Check whether the given Object contains in the hashTable
    public boolean contains(Object obj)
    {
        return hashTable.contains(obj);
    }

    // Returns true if the hashtable contains given value otherwise return false
    public boolean containsValue(Object val)
    {
        return hashTable.containsValue(val);
    }

    // Returns true if the hashTable contains given key otherwise return false
    public boolean containsKey(Object key)
    {
        return hashTable.containsKey(key);
    }

    // Returns an enumeration of the values in the hashtable
    public Enumeration<V> elements()
    {
        return hashTable.elements();
    }

    // Returns a set of entry of hashTable
    public Set<Map.Entry<K, V>> entrySet()
    {
        return hashTable.entrySet();
    }

    // Return true if hashTable equals to the given Object
    public boolean equals(Object obj)
    {  
        return hashTable.equals(obj);
    }

    // Returns the value to which the specified key is mapped, 
    // or null if the map contains no mapping for the key.
    public V get(Object key)
    {
        return hashTable.get(key);
    }

    // Returns the hash code value for the Map 
    public int hashCode()
    {
        return hashTable.hashCode();
    }

    // Check whether hashTable is empty or not
    public boolean isEmpty()
    {
        return hashTable.isEmpty();
    }

    // Returns an enumeration of the keys in on the hashtable
    public Enumeration<K> keys()
    {
        return hashTable.keys();
    }

    // Returns a Set view of the keys
    public Set<K> keySet()
    {
        return hashTable.keySet();
    }

    // Maps the specified key to the specified value in this hashTable
    public V put(K key, V val)
    {
        return hashTable.put(key, val);
    }

    // Returns the number of keys in the hashtable
    public int size()
    {
        return hashTable.size();
    }

    //Returns a string representation of the Hashtable objects in the form of String
    public String toString()
    {
        return hashTable.toString();
    }

    // Removes the given key with the value from the hashTable
    public V remove(Object key)
    {
        return hashTable.remove(key);
    }

    // Returns a Collection view of the values
    public Collection<V> values()
    {
        return hashTable.values();
    }
}
public class GFG{ 
    public static void main(String[] arg)
    {
        HashTableImplementation<String, Integer> hashTable = 
                         new HashTableImplementation<>();

        // Add elements to hashTable
        hashTable.put("Nikhil", 390);
        hashTable.put("Akshay", 280);
        hashTable.put("Bina", 500);
        hashTable.put("Chintu", 450);

        // Print the size of the hashTable
        System.out.println("The size of the hashTable: " + hashTable.size());

        // Iterate and print the EntrySet of the hashTable
        System.out.println("Entry Set of the hashTable: ");
        Set<Entry<String, Integer>> entrySet = hashTable.entrySet();
        Iterator<Entry<String, Integer>> entry = entrySet.iterator();

        while (entry.hasNext())
        {
            System.out.println(entry.next() + " ");
        }
        System.out.println();

        // Iterate and print the keys of the hashTable
        System.out.println("The keys of the HashTable: ");

        Set<String> keySet = hashTable.keySet();

        Iterator<String> it = keySet.iterator();

        while (it.hasNext())
        {
            System.out.print(it.next() + " ");
        }
        System.out.println();

        // Iterate and print the value of the hashTable
        System.out.println("The values of the HashTable:");

        Collection<Integer> values = hashTable.values();

        Iterator<Integer> itr = values.iterator();
        while (itr.hasNext())
        {
            System.out.print(itr.next() + " ");
        }
        System.out.println();

        // Print true if hashTable contains the key "Nikhil" 
        System.out.println("The hashTable contains Nikhil: "
                           + hashTable.containsKey("Nikhil"));

        // Delete all the entrys
        hashTable.clear();

        // Print size of the hashTable
        System.out.println("The size of the hashTable: " 
                           + hashTable.size());

    }
}
```

**Output**

```
The size of the hashTable: 4
Entry Set of the hashTable: 
Chintu=450 
Nikhil=390 
Akshay=280 
Bina=500 

The keys of the HashTable: 
Chintu Nikhil Akshay Bina 
The values of the HashTable:
450 390 280 500 
The hashTable contains Nikhil: true
The size of the hashTable: 0
```