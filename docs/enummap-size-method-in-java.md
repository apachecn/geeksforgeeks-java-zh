# Java 中的 EnumMap size()方法

> 原文:[https://www.geeksforgeeks.org/enummap-size-method-in-java/](https://www.geeksforgeeks.org/enummap-size-method-in-java/)

Java 中的 Java.util.EnumMap.size()方法用于知道地图的大小或地图中存在的元素数量。

**语法:**

```
Enum_Map.size()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回地图的大小。

以下程序说明了 size()函数的工作:
**程序 1:**

```
// Java program to demonstrate size()
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {
    India_today,
    United_States_today
}
;

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp = new 
                    EnumMap<gfg, Integer>(gfg.class);

        // Values are associated
        mp.put(gfg.India_today, 69);
        mp.put(gfg.United_States_today, 1073);

        // Prints the map
        System.out.println("The EnumMap: " + mp);

        // Store the size of the map
        int numberOf_kv = mp.size();

        // Prints the map_size
        System.out.println("Size of map: " + numberOf_kv);
    }
}
```

**Output:**

```
The EnumMap: {India_today=69, United_States_today=1073}
Size of map: 2

```

**程序 2:**

```
// Java program to demonstrate size()
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {

    India_today,
    United_States_today
}
;

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp = new 
                  EnumMap<gfg, Integer>(gfg.class);

        // Values are associated
        mp.put(gfg.India_today, 69);
        mp.put(gfg.United_States_today, 1073);

        // Prints the map
        System.out.println("The EnumMap: " + mp);

        // Remove mapping of this key
        mp.remove(gfg.United_States_today);

        // Prints the final map
        System.out.println("The EnumMap: " + mp);

        // Store the size pf map after removal of
        // The key
        int numberOf_kv = mp.size();

        // Prints the map_size
        System.out.println("Size of map: " + numberOf_kv);
    }
}
```

**Output:**

```
The EnumMap: {India_today=69, United_States_today=1073}
The EnumMap: {India_today=69}
Size of map: 1

```