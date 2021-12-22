# Java 中的 EnumMap putAll(map)方法

> 原文:[https://www . geesforgeks . org/enummap-putallmap-method-in-Java/](https://www.geeksforgeeks.org/enummap-putallmap-method-in-java/)

Java 中的 Java . util . enummap . putall(*map*)方法用于将一个映射中的所有映射复制到一个更新的映射中。旧的映射被新的映射替换。

**语法:**

```
void putAll(*map*)
```

**参数:**该方法取一个参数*映射*。这是要复制到新地图上的地图。

**返回值**该方法不返回值。

下面的程序说明了 putAll()方法:

**程序 1:**

```
// Java program to demonstrate keySet()
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {
    Global_today,
    India_today,
    China_today
};

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp1 = 
                     new EnumMap<gfg, Integer>(gfg.class);

        EnumMap<gfg, Integer> mp2 = 
                     new EnumMap<gfg, Integer>(gfg.class);

        // Values are associated
        mp1.put(gfg.Global_today, 799);
        mp1.put(gfg.India_today, 69);

        // Copies all the mappings of mp1 to mp2
        mp2.putAll(mp1);

        // Prints the first map
        System.out.println("Mappings in Map1: " + mp1);

        // Prints the second map
        System.out.println("Mappings in Map2: " + mp2);
    }
}
```

**Output:**

```
Mappings in Map1: {Global_today=799, India_today=69}
Mappings in Map2: {Global_today=799, India_today=69}

```

**程序 2:**

```
// Java program to demonstrate the working of keySet()
import java.util.*;

// an enum of geeksforgeeks
// visitors in India and United States
public enum gfg {

    India_today,
    United_States_today
}
;

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, String> mp1 = 
                     new EnumMap<gfg, String>(gfg.class);

        EnumMap<gfg, String> mp2 = 
                     new EnumMap<gfg, String>(gfg.class);

        // Values are associated
        mp1.put(gfg.India_today, "61.8%");
        mp1.put(gfg.United_States_today, "18.2%");

        // Copies all the mappings of mp1 to mp2
        mp2.putAll(mp1);

        // Prints the first map
        System.out.println("Mappings in Map1: " + mp1);

        // Prints the second map
        System.out.println("Mappings in Map2: " + mp2);
    }
}
```

**Output:**

```
Mappings in Map1: {India_today=61.8%, United_States_today=18.2%}
Mappings in Map2: {India_today=61.8%, United_States_today=18.2%}

```