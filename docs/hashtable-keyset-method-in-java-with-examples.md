# Java 中的哈希表键集()方法，带示例

> 原文:[https://www . geesforgeks . org/hashtable-key set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/hashtable-keyset-method-in-java-with-examples/)

哈希表 用于在哈希表中创建一组关键元素。它基本上返回一个键的集合视图，或者我们可以创建一个新的集合并将关键元素存储在其中。

**语法:**

```
public Set<K> keySet()
```

**K** :哈希表中键的类型

**参数:**该方法不取任何参数。

**返回值:**该方法返回一个具有哈希表关键字的集合。

下面的程序用来说明 java.util.Hashtable.keySet()的工作方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the keySet() method
// to get Set view of Keys from a Hashtable.

import java.util.Enumeration;
import java.util.Iterator;
import java.util.Hashtable;
import java.util.Set;

public class Example1 {

    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<String, String> hash_t
            = new Hashtable<String, String>();

        // Add mappings into the table
        hash_t.put("1", "Geeks");
        hash_t.put("2", "For");
        hash_t.put("3", "Geeks");

        // Getting a Set of keys using
        // keySet() method of Hashtable class
        Set hash_set = hash_t.keySet();

        System.out.println(
            "Set created from Hashtable Keys contains :");

        // Iterating through the Set of keys
        Iterator itr = hash_set.iterator();
        while (itr.hasNext())
            System.out.println(itr.next());
    }
}
```

**Output**

```
Set created from Hashtable Keys contains :
3
2
1
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to illustrate the keySet() method
// to get Set view of Keys from a Hashtable.

import java.util.Enumeration;
import java.util.Iterator;
import java.util.Hashtable;
import java.util.Set;

public class Example2 {

    public static void main(String[] args)
    {

        // Creating an empty Hashtable
        Hashtable<String, String> hash_t
            = new Hashtable<String, String>();

        // Inserting elements into the table
        hash_t.put("Geeks", "1");
        hash_t.put("For", "2");
        hash_t.put("geeks", "3");

        // Getting a Set of keys using
        // keySet() method of Hashtable class
        Set hash_set = hash_t.keySet();

        System.out.println(
            "Set created from Hashtable Keys contains :");

        // Iterating through the Set of keys
        Iterator itr = hash_set.iterator();
        while (itr.hasNext())
            System.out.println(itr.next());
    }
}
```

**Output**

```
Set created from Hashtable Keys contains :
For
Geeks
geeks
```

**注意:** 相同的操作可以用不同数据类型的变化和组合的任何类型的映射来执行。