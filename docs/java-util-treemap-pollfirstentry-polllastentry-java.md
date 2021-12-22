# Java 中的 Java . util . treemap . pollfirstentry()和 pollLastEntry()

> 原文:[https://www . geesforgeks . org/Java-util-tree map-pollfirstentry-pollasterentry-Java/](https://www.geeksforgeeks.org/java-util-treemap-pollfirstentry-polllastentry-java/)

Java.util.TreeMap 还包含支持在值的高端和低端进行检索和删除的功能，因此在适用性和日常使用方面具有很大的灵活性。这个函数是 poll()，在本文中讨论了 2 个变体。

**1。pollFirstEntry() :** 它**移除并检索一个键值对**，其中**是地图中键值最少的**，而**“空”**是地图为空。

```java
Syntax : 
public Map.Entry pollFirstEntry()
Parameters:
NA
Return Value:
Retrieves and removes the least key-value if map is filled else returns null.
Exception:
NA

```

```java
// Java code to demonstrate the working
// of pollFirstEntry()
import java.io.*;
import java.util.*;
public class pollFirstEntry {
    public static void main(String[] args)
    {

        // Declaring the tree map of String and Integer
        TreeMap<String, Integer> tmp = new TreeMap<String, Integer>();

        // Trying to retrieve and remove in empty map
        // returns null
        System.out.println
        ("The smallest key value pair is : " + tmp.pollFirstEntry());

        // assigning the values in the tree map
        // using put()
        tmp.put("Geeks", 1);
        tmp.put("for", 4);
        tmp.put("geeks", 1);

        // Printing the initial map
        System.out.println
        ("The initial Map before deletion is : " + tmp);

        // Use of pollFirstEntry()
        // Removes the first entry and returns the least key
        // lexicographically smallest in case of String
        // prints Geeks-1
        System.out.println
        ("The smallest key value pair is : " + tmp.pollFirstEntry());

        // Printing the map after deletion
        System.out.println
        ("The resultant Map after deletion is : " + tmp);
    }
}
```

输出:

```java
The smallest key value pair is : null
The initial Map before deletion is : {Geeks=1, for=4, geeks=1}
The smallest key value pair is : Geeks=1
The resultant Map after deletion is : {for=4, geeks=1}

```

**2。pollasterentry():**它**移除并检索一个键值对**，其中**是地图中最大的键值**，**“空”**是地图为空。

```java
Syntax : 
public Map.Entry pollLastEntry()
Parameters:
NA
Return Value:
Retrieves and removes the largest key-value if map is filled else returns null.
Exception:
NA

```

```java
// Java code to demonstrate the working
// of pollLastEntry()
import java.io.*;
import java.util.*;
public class pollLastEntry {
    public static void main(String[] args)
    {

        // Declaring the tree map of String and Integer
        TreeMap<String, Integer> tmp = new TreeMap<String, Integer>();

        // Trying to retrieve and remove in empty map
        // returns null
        System.out.println
        ("The largest key value pair is : " + tmp.pollFirstEntry());

        // assigning the values in the tree map
        // using put()
        tmp.put("Geeks", 1);
        tmp.put("for", 4);
        tmp.put("geeks", 1);

        // Printing the initial map
        System.out.println
        ("The initial Map before deletion is : " + tmp);

        // Use of pollLastEntry()
        // Removes the last(max) entry and returns the max key
        // lexicographically greatest in case of String
        // prints geeks-1
        System.out.println
        ("The largest key value pair is : " + tmp.pollLastEntry());

        // Printing the map after deletion
        System.out.println
        ("The resultant Map after deletion is : " + tmp);
    }
}
```

输出:

```java
The largest key value pair is : null
The initial Map before deletion is : {Geeks=1, for=4, geeks=1}
The largest key value pair is : geeks=1
The resultant Map after deletion is : {Geeks=1, for=4}

```

**实际应用:**使用去重或优先排队的概念可以想到很多应用。下面的代码显示了一个这样的例子。

```java
// Java code to demonstrate the application
// of pollLastEntry() and pollFirstEntry()
import java.io.*;
import java.util.*;
public class pollAppli {
    public static void main(String[] args)
    {

        // Declaring the tree map of Integer and String
        TreeMap<Integer, String> que = new TreeMap<Integer, String>();

        // assigning the values in que
        // using put()
        que.put(10, "astha");
        que.put(4, "shambhavi");
        que.put(7, "manjeet");
        que.put(8, "nikhil");

        // Defining the priority
        // takes highest value, if priority is high
        // else takes lowest value
        String prio = "high";

        // Printing the initial queue
        System.out.println("The initial queue is : " + que);
        if (prio == "high") {
            System.out.println
            ("The largest valued person is : " + que.pollLastEntry());
            System.out.println
            ("The resultant queue after deletion is : " + que);
        }
        else {
            System.out.println
            ("The lowest valued person is : " + que.pollFirstEntry());
            System.out.println
            ("The resultant queue after deletion is : " + que);
        }
    }
}
```

输出:

```java
The initial queue is : {4=shambhavi, 7=manjeet, 8=nikhil, 10=astha}
The largest valued person is : 10=astha
The resultant queue after deletion is : {4=shambhavi, 7=manjeet, 8=nikhil}

```