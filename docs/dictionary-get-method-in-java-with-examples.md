# Java 中的字典 get()方法，带示例

> 原文:[https://www . geesforgeks . org/dictionary-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/dictionary-get-method-in-java-with-examples/)

Dictionary 类的 get()方法用于检索或获取由参数中提到的特定键映射的值。当字典不包含键的这种映射时，它返回空值。

**语法:**

```
DICTIONARY.get(Object key_element)
```

**参数:**该方法取一个对象类型的参数 *key_element* ，指的是应该取其关联值的键。

**返回值:**该方法返回与参数中 key_element 关联的值。

以下程序用于说明 java.util.Dictionary.get()方法:
**程序 1:**

```
// Java code to illustrate the get() method
import java.util.*;

public class Dictionary_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Dictionary
        Dictionary<Integer, String> dict
            = new Hashtable<Integer, String>();

        // Inserting the values into dictionary
        dict.put(10, "Geeks");
        dict.put(15, "4");
        dict.put(20, "Geeks");
        dict.put(25, "Welcomes");
        dict.put(30, "You");

        // Displaying the Dictionary
        System.out.println("Initial Dictionary is: " + dict);

        // Getting the value of 25
        System.out.println("The Value is: " + dict.get(25));

        // Getting the value of 10
        System.out.println("The Value is: " + dict.get(10));
    }
}
```

**Output:**

```
Initial Dictionary is: {10=Geeks, 20=Geeks, 30=You, 15=4, 25=Welcomes}
The Value is: Welcomes
The Value is: Geeks

```

**程序 2:**

```
// Java code to illustrate the get() method
import java.util.*;

public class Dictionary_Demo {
    public static void main(String[] args)
    {

        // Creating an empty Dictionary
        Dictionary<String, Integer> dict
            = new Hashtable<String, Integer>();

        // Inserting the values into dictionary
        dict.put("Geeks", 10);
        dict.put("4", 15);
        dict.put("Geeks", 20);
        dict.put("Welcomes", 25);
        dict.put("You", 30);

        // Displaying the Dictionary
        System.out.println("Initial Dictionary is: "
                           + dict);

        // Getting the value of 25
        System.out.println("The Value is: "
                           + dict.get("Geeks"));

        // Getting the value of 10
        System.out.println("The Value is: "
                           + dict.get(20));
    }
}
```

**Output:**

```
Initial Dictionary is: {You=30, Welcomes=25, 4=15, Geeks=20}
The Value is: 20
The Value is: null

```