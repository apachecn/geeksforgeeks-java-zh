# Java 中的 EnumMap keySet()方法

> 原文:[https://www . geesforgeks . org/enummap-key set-method-in-Java/](https://www.geeksforgeeks.org/enummap-keyset-method-in-java/)

Java 中的 Java.util.EnumMap.keySet()方法用于返回映射中包含的键的集合视图。

**语法:**

```
Enum_Map.keySet()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回地图中包含的关键点的集合视图。

下面的程序说明了 keySet()函数:

**程序 1:**

```
// Java program to demonstrate keySet()
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {
    India,
    United_States,
    China
};

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, String> mp = new 
                    EnumMap<gfg, String>(gfg.class);

        // Values are associated
        mp.put(gfg.India, "61.7%");
        mp.put(gfg.United_States, "18.2%");
        mp.put(gfg.China, "2.5%");

        // Prints the map
        System.out.println("Mappings: " + mp);

        // Store the set view of the key
        Set<gfg> set_view = mp.keySet();

        // Print the result
        System.out.println("Set view of the key: " + 
                                            set_view);
    }
}
```

**Output:**

```
Mappings: {India=61.7%, United_States=18.2%, China=2.5%}
Set view of the key: [India, United_States, China]

```

**程序 2:**

```
// Java program to demonstrate keySet()
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {
    Global_today,
    India_today
};

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp = 
                new EnumMap<gfg, Integer>(gfg.class);

        // Values are associated
        mp.put(gfg.Global_today, 799);
        mp.put(gfg.India_today, 69);

        // Prints the map
        System.out.println("Mappings: " + mp);

        // Store the set view of the key
        Set<gfg> set_view = mp.keySet();

        // Print the result
        System.out.println("Set view of the key: " +
                                             set_view);
    }
}
```

**Output:**

```
Mappings: {Global_today=799, India_today=69}
Set view of the key: [Global_today, India_today]

```