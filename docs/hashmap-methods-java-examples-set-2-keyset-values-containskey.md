# Java 中的 Hashmap 方法，示例| Set 2 (keySet()，values()，containsKey()..)

> 原文:[https://www . geesforgeks . org/hashmap-methods-Java-examples-set-2-key set-values-contains key/](https://www.geeksforgeeks.org/hashmap-methods-java-examples-set-2-keyset-values-containskey/)

[Java 中的 HashMap 类方法，示例| Set 1 (put()、get()、isEmpty()和 size())](https://www.geeksforgeeks.org/hashmap-class-methods-java-examples-set-1-put-get-isempty-size/)

这篇文章讨论了更多的方法。

*   **KeySet():****Java . util . HashMap . KeySet()**它返回此地图中包含的键的集合视图。集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。

    ```java
    Syntax:
    public Set keySet()
    Return: a set view of the keys contained in this map

    ```

*   **values():****Java . util . hashmap . values()**它返回此地图中包含的值的集合视图。集合由地图支持，因此对地图的更改会反映在集合中，反之亦然。

```java
Syntax:
public Collection values()
Return: a collection view of the values contained in 
this map

```

*   **containsKey():** **java.util.HashMap.containsKey()** It returns true if this map maps one or more keys to the specified value.

    ```java
    Syntax:
    public boolean containsValue(Object value)
    Parameters:
    value - value whose presence in this map is to be tested
    Return: true if this map maps one or more keys to 
    the specified value

    ```

    实施:

    ```java
    // Java program illustrating usage of HashMap class methods
    // keySet(), values(), containsKey()
    import java.util.*;
    public class NewClass
    {
        public static void main(String args[])
        {
            // 1   Creation of HashMap
            HashMap<String, String> Geeks = new HashMap<>();

            // 2   Adding values to HashMap as ("keys", "values")
            Geeks.put("Language", "Java");
            Geeks.put("Platform", "Geeks For geeks");
            Geeks.put("Code", "HashMap");
            Geeks.put("Learn", "More");

            // 3  containsKey() method is to check the presence
            //    of a particluar key
            // Since 'Code' key present here, the condition is true
            if (Geeks.containsKey("Code"))
                System.out.println("Testing .containsKey : " +
                                               Geeks.get("Code"));

            // 4 keySet() method returns all the keys in HashMap
            Set<String> Geekskeys = Geeks.keySet();
            System.out.println("Initial keys  : " + Geekskeys);

            // 5  values() method return all the values in HashMap
            Collection<String> Geeksvalues = Geeks.values();
            System.out.println("Initial values : " + Geeksvalues);

            // Adding new set of key-value
            Geeks.put("Search", "JavaArticle");

            // Again using .keySet() and .values() methods
            System.out.println("New Keys : " + Geekskeys);
            System.out.println("New Values: " + Geeksvalues);
        }
    }
    ```

    输出:

    ```java
    Testing .containsKey : HashMap
    Initial keys  : [Language, Platform, Learn, Code]
    Initial values : [Java, Geeks For geeks, More, HashMap]
    New Keys : [Language, Platform, Search, Learn, Code]
    New Values: [Java, Geeks For geeks, JavaArticle, More, HashMap]

    ```

    *   **。entrySet():****Java . util . HashMap . entrySet()**方法返回 HashMap 中存在的一组完整的键和值。

    ```java
    Syntax:
    public Set<Map.Entry> entrySet()
    Return:
    complete set of keys and values

    ```

    *   **。getOrDefault:****Java . util . HashMap . getOrDefault()**如果使用我们在 HashMap 中作为参数传递的键没有值 find，则方法返回默认值。如果键的值已经存在于 HashMap 中，它不会对它做任何事情。
    为尚未映射的键赋值是非常好的方法，不会干扰已经存在的键和值集。

    ```java
    Syntax:
    default V getOrDefault(Object key,V defaultValue)
    Parameters:
    key - the key whose mapped value we need to return
    defaultValue - the default for the keys present in HashMap
    Return:
    mapping the unmapped keys with the default value.

    ```

    *   **。replace():****java.util.HashMap . replace(key，value)** 或**Java . util . hashmap . replace(key，oldvalue，newvalue)** 方法是一个 Java . util . hashmap 类方法。
    第一个方法接受一组键和值，用参数中传递的新值替换键的现有值。如果不存在这样的集合，replace()方法将不做任何事情。
    同时，如果在哈希表中找到键和旧值，第二种方法将只替换已经存在的键-旧值集。

    ```java
    Syntax:
    replace(k key, v value)
              or
    replace(k key, v oldvalue, newvalue)
    Parameters:
    key      - key in set with the old value.
    value    - new value we want to be with the specified key
    oldvalue - old value in set with the specified key
    newvalue - new value we want to be with the specified key
    Return:
    True - if the value is replaced
    Null - if there is no such set present

    ```

    *   **.putIfAbsent** **java.util.HashMap.putIfAbsent(key, value)** method is being used to insert a new key-value set to the HashMap if the respective set is present. Null value is returned if such key-value set is already present in the HashMap.

    ```java
    Syntax:
    public V putIfAbsent(key, value)
    Parameters:
    key      - key with which the specified value is associates.
    value    - value to associates with the specified key.

    ```

    ```java
    // Java Program illustrating HashMap class methods(). 
    // entrySet(), getOrDefault(), replace(), putIfAbsent
    import java.util.*;
    public class NewClass
    {
        public static void main(String args[])
        {
            // Creation of HashMap
            HashMap<String, String> Geeks = new HashMap<>();

            // Adding values to HashMap as ("keys", "values")
            Geeks.put("Language", "Java");
            Geeks.put("Code", "HashMap");
            Geeks.put("Learn", "More");

            // .entrySet() returns all the keys with their values present in Hashmap
            Set<Map.Entry<String, String>> mappingGeeks = Geeks.entrySet();
            System.out.println("Set of Keys and Values using entrySet() : "+mappingGeeks);
            System.out.println();

            // Using .getOrDefault to access value
            // Here it is Showing Default value as key - "Code" was already present
            System.out.println("Using .getorDefault : " 
                                        + Geeks.getOrDefault("Code","javaArticle"));

            // Here it is Showing set value as key - "Search" was not present
            System.out.println("Using .getorDefault : "
                                        + Geeks.getOrDefault("Search","javaArticle"));
            System.out.println();

            // .replace() method replacing value of key "Learn"
            Geeks.replace("Learn", "Methods");
            System.out.println("working of .replace()     : "+mappingGeeks);
            System.out.println();

            /* .putIfAbsent() method is placing a new key-value
                as they were not present initially*/
            Geeks.putIfAbsent("cool", "HashMap methods");
            System.out.println("working of .putIfAbsent() : "+mappingGeeks);

            /* .putIfAbsent() method is not doing anything
                as key-value were already present */
            Geeks.putIfAbsent("Code", "With_JAVA");
            System.out.println("working of .putIfAbsent() : "+mappingGeeks);

        }
    }
    ```

    **输出:**

    ```java
    Set of Keys and Values using entrySet() : [Language=Java, Learn=More, Code=HashMap]

    Using .getorDefault : HashMap
    Using .getorDefault : javaArticle

    working of .replace()     : [Language=Java, Learn=Methods, Code=HashMap]

    working of .putIfAbsent() : [Language=Java, cool=HashMap methods, Learn=Methods, Code=HashMap]
    working of .putIfAbsent() : [Language=Java, cool=HashMap methods, Learn=Methods, Code=HashMap]

    ```

    *   **remove(Object key):** Removes the mapping for this key from this map if present.

    ```java
    // Java Program illustrating remove() method using Iterator.

    import java.util.*;
    public class NewClass
    {
        public static void main(String args[])
        {
            //  Creation of HashMap
            HashMap<String, String> Geeks = new HashMap<>();

            //  Adding values to HashMap as ("keys", "values")
            Geeks.put("Language", "Java");
            Geeks.put("Platform", "Geeks For geeks");
            Geeks.put("Code", "HashMap");

            //  .entrySet() returns all the keys with their values present in Hashmap
            Set<Map.Entry<String, String>> mappingGeeks = Geeks.entrySet();
            System.out.println("Set of Keys and Values : "+mappingGeeks);
            System.out.println();

            //  Creating an iterator
            System.out.println("Use of Iterator to remove the sets.");
            Iterator<Map.Entry<String, String>> geeks_iterator = Geeks.entrySet().iterator();
            while(geeks_iterator.hasNext())
            {
                Map.Entry<String, String> entry = geeks_iterator.next();
                //  Removing a set one by one using iterator
                geeks_iterator.remove(); // right way to remove entries from Map,
                // avoids ConcurrentModificationException
                System.out.println("Set of Keys and Values : "+mappingGeeks);

            }
        }
    }
    ```

    **输出:**

    ```java
    Set of Keys and Values : [Language=Java, Platform=Geeks For geeks, Code=HashMap]

    Use of Iterator to remove the sets.
    Set of Keys and Values : [Platform=Geeks For geeks, Code=HashMap]
    Set of Keys and Values : [Code=HashMap]
    Set of Keys and Values : []

    ```

    **优势:**
    如果我们使用 for 循环，它会在内部被翻译成迭代器，但是如果不显式使用迭代器，我们就不能在迭代过程中移除任何条目。这样做时，迭代器可能会抛出 ConcurrentModificationException。因此，我们使用显式迭代器和 while 循环来遍历。

    **参考:**
    [https://docs . Oracle . com/javase/7/docs/API/Java/util/hashmap . html](https://docs.oracle.com/javase/7/docs/api/java/util/HashMap.html)

    本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。