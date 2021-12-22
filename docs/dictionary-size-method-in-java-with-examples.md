# Java 中的字典大小()方法，带示例

> 原文:[https://www . geesforgeks . org/dictionary-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dictionary-size-method-in-java-with-examples/)

Java 中 Dictionary 类的 size()方法用于知道字典的大小或字典中存在的不同键的数量。

**语法:**

```java
DICTIONARY.size()
```

**参数:**
该方法不接受任何参数。

**返回值:**
该方法返回字典中存在的键的数量。

下面的程序说明了字典的大小()方法:
**程序 1:**

```java
// Java Code to illustrate size()
import java.util.*;

public class Dictionary_Demo {
    public static void main(String args[])
    {

        // Creating a dictionary of Hashtable
        Dictionary<Integer, String> dict
            = new Hashtable<Integer, String>();

        // Inserting elements into the Dictionary
        dict.put(10, "Geeks");
        dict.put(15, "4");
        dict.put(10, "Geeks");
        dict.put(25, "Welcomes");
        dict.put(30, "You");

        // Displaying the Dictionary
        System.out.println("Dictionary: " + dict);

        // Displaying the size of the dictionary
        System.out.println("The size of the dictionary is "
                           + dict.size());
    }
}
```

**Output:**

```java
Dictionary: {10=Geeks, 30=You, 15=4, 25=Welcomes}
The size of the dictionary is 4

```

**程序 2:**

```java
// Java Code to illustrate size()
import java.util.*;

public class Dictionary_Demo {
    public static void main(String args[])
    {

        // Creating a dictionary of Hashtable
        Dictionary<String, Integer> dict
            = new Hashtable<String, Integer>();

        // Inserting elements into the table
        dict.put("Geek", 10);
        dict.put("4", 15);
        dict.put("Geeks", 20);
        dict.put("Welcomes", 25);
        dict.put("You", 30);

        // Displaying the Dictionary
        System.out.println("Dictionary: " + dict);

        // Displaying the size of the dictionary
        System.out.println("The size of the dictionary is "
                           + dict.size());
    }
}
```

**Output:**

```java
Dictionary: {You=30, Welcomes=25, 4=15, Geeks=20, Geek=10}
The size of the dictionary is 5

```