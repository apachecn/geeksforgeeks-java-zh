# Java 中的 EnumMap put()方法

> 原文:[https://www.geeksforgeeks.org/enummap-put-method-in-java/](https://www.geeksforgeeks.org/enummap-put-method-in-java/)

Java 中的 Java.util.EnumMap.put( *键，值*)方法用于关联指定的键值对。在这种情况下，如果重复这些值，旧的值将被替换。

**语法:**

```
Enum_Map.put(*key, value*)
```

**使用的参数:**该方法采用两个参数。

*   *键*–它是与值相关联的指定键。
*   *值*–它是与指定键相关联的值。

**返回值:**函数返回与指定键相关的旧值。

以下程序说明了 put( *键，value* )的工作方法:
**程序 1:**

```
// Java program to demonstrate keySet()
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {
    Global_today,
    India_today,
    China
}
;

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp = new 
                 EnumMap<gfg, Integer>(gfg.class);

        // Values are associated
        mp.put(gfg.Global_today, 799);
        mp.put(gfg.India_today, 69);

       // Display the initial map
       System.out.println("The map is: " + mp);

        // Stores the old value associated with the key
        int prev_value = mp.put(gfg.India_today, 72);

        // Prints the old value
        System.out.println("Previous value: " + prev_value);

       // Display the final map
       System.out.println("The final map is: " + mp);
    }
}
```

**Output:**

```
The map is: {Global_today=799, India_today=69}
Previous value: 69
The final map is: {Global_today=799, India_today=72}

```

**程序 2:**

```
// Java program to demonstrate the working of keySet()
import java.util.*;

// an enum of geeksforgeeks
// ranking globally and in india
public enum gfg {
    Global_today,
    India_today,
    China_today
}
;

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp = new EnumMap<gfg, Integer>(gfg.class);

        // Values are associated
        mp.put(gfg.Global_today, 799);
        mp.put(gfg.India_today, 69);

       // Display the initial map
       System.out.println("The map is: " + mp);

        // Stores the old value associated with the key
        int prev_value = mp.put(gfg.Global_today, 800);

        // Prints the old value
        System.out.println("Previous value: " + prev_value);

       // Display the final map
       System.out.println("The final map is: " + mp);
    }
}
```

**Output:**

```
The map is: {Global_today=799, India_today=69}
Previous value: 799
The final map is: {Global_today=800, India_today=69}

```