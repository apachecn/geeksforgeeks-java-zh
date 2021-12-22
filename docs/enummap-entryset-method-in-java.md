# Java 中的 EnumMap entrySet()方法

> 原文:[https://www . geesforgeks . org/enummap-entryset-method-in-Java/](https://www.geeksforgeeks.org/enummap-entryset-method-in-java/)

Java 中的 Java.util.EnumMap.entrySet()方法用于创建一组包含在 EnumMap 中的元素。它基本上返回枚举映射的集合视图。

**语法:**

```
enum_map.entrySet()
```

**参数:**该方法不取任何参数。

**返回值:**该方法返回此 enum_map 中包含的映射的集合视图。

下面的程序说明了 entrySet()方法:

**程序 1:**

```
// Java program to demonstrate entrySet() method
import java.util.*;

// An enum of gfg rank is created
public enum rank_countries {
    India,
    United_States,
    China,
    Japan,
    Canada,
    Russia
}
;

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<rank_countries, Integer> mp = new 
        EnumMap<rank_countries, Integer>(rank_countries.class);

        // Values are associated in mp
        mp.put(rank_countries.India, 72);
        mp.put(rank_countries.United_States, 1083);
        mp.put(rank_countries.China, 4632);
        mp.put(rank_countries.Japan, 6797);

        // Map view
        System.out.println("Map view: " + mp);

        // Creating a new set of the mappings
        // contained in map
        Set<Map.Entry<rank_countries, Integer> > set_view = 
                                                mp.entrySet();

        // Set view of the mappings
        System.out.println("Set view of the map: " + set_view);
    }
}
```

**Output:**

```
Map view: {India=72, United_States=1083, China=4632, Japan=6797}
Set view of the map: [India=72, United_States=1083, China=4632, Japan=6797]

```

**程序 2:**

```
// Java program to demonstrate entrySet() method
import java.util.*;

// An enum of gfg ranking worldwide and in india
public enum gfg {
    Global_2018,
    India_2018
};

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp = new 
              EnumMap<gfg, Integer>(gfg.class);

        // Values are associated in mp
        mp.put(gfg.Global_2018, 800);
        mp.put(gfg.India_2018, 72);

        // Mapping view
        System.out.println("Mapping view: " + mp);

        // Creating a new set of the mappings 
        Set<Map.Entry<gfg, Integer> > set_view = 
                                    mp.entrySet();

        // Set view of the mappings
        System.out.println("Set view of the map: "
                                      + set_view);
    }
}
```

**Output:**

```
Mapping view: {Global_2018=800, India_2018=72}
Set view of the map: [Global_2018=800, India_2018=72]

```