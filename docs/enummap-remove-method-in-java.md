# Java 中的 EnumMap remove()方法

> 原文:[https://www . geesforgeks . org/enummap-remove-method-in-Java/](https://www.geeksforgeeks.org/enummap-remove-method-in-java/)

Java 中的 Java.util.EnumMap.remove( *键*)方法用于从地图中移除指定的键。

**语法:**

```java
remove(*Object key*)
```

**参数:**该方法取一个参数*键*，指的是要去掉映射的键。

**返回值:**该方法不返回值。

以下程序说明了清除(*键*)功能的工作:
**程序 1:**

```java
// Java program to demonstrate remove()
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

        EnumMap<gfg, String> mp = new 
                  EnumMap<gfg, String>(gfg.class);

        // Values are associated
        mp.put(gfg.India_today, "61.8%");
        mp.put(gfg.United_States_today, "18.2%");

        // Prints the map
        System.out.println("The EnumMap: " + mp);

        // Remove mapping of this key
        mp.remove(gfg.United_States_today);

        // Prints the final map
        System.out.println("Map after removal: " + mp);
    }
}
```

**Output:**

```java
The EnumMap: {India_today=61.8%, United_States_today=18.2%}
Map after removal: {India_today=61.8%}

```

**程序 2:**

```java
// Java program to demonstrate the working of keySet()
import java.util.*;

// an enum of geeksforgeeks
// rank in India and United States
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
        System.out.println("Map after removal: " + mp);
    }
}
```

**Output:**

```java
The EnumMap: {India_today=69, United_States_today=1073}
Map after removal: {India_today=69}

```