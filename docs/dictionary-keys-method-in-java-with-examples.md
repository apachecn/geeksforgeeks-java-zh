# Java 中的字典键()方法，带示例

> 原文:[https://www . geesforgeks . org/dictionary-key-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dictionary-keys-method-in-java-with-examples/)

Java 中 Dictionary 类的 keys()方法用于获取字典中存在的键的枚举。

**语法:**

```
Enumeration enu = DICTIONARY.keys()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回字典键的枚举。

下面的程序用来说明 java.util.Dictionary.keys()方法的工作:
**程序 1:**

```
// Java code to illustrate the keys() method
import java.util.*;

public class Dictionary_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Dictionary
        Dictionary<Integer, String> dict
            = new Hashtable<Integer, String>();

        // Inserting elements into the Dictionary
        dict.put(10, "Geeks");
        dict.put(15, "4");
        dict.put(20, "Geeks");
        dict.put(25, "Welcomes");
        dict.put(30, "You");

        // Displaying the Dictionary
        System.out.println("The Dictionary is: " + dict);

        // Creating an empty enumeration to store
        Enumeration enu = dict.keys();

        System.out.println("The enumeration of keys are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**Output:**

```
The Dictionary is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
The enumeration of keys are:
10
20
30
15
25

```

**程序 2:**

```
// Java code to illustrate the keys() method
import java.util.*;

public class Dictionary_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Dictionary
        Dictionary<String, Integer> dict
            = new Hashtable<String, Integer>();

        // Inserting elements into the table
        dict.put("Geeks", 10);
        dict.put("4", 15);
        dict.put("Geeks", 20);
        dict.put("Welcomes", 25);
        dict.put("You", 30);

        // Displaying the Dictionary
        System.out.println("The Dictionary is: " + dict);

        // Creating an empty enumeration to store
        Enumeration enu = dict.keys();

        System.out.println("The enumeration of keys are:");

        // Displaying the Enumeration
        while (enu.hasMoreElements()) {
            System.out.println(enu.nextElement());
        }
    }
}
```

**Output:**

```
The Dictionary is: {You=30, Welcomes=25, 4=15, Geeks=20}
The enumeration of keys are:
You
Welcomes
4
Geeks

```