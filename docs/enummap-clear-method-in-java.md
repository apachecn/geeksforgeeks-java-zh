# Java 中的 EnumMap clear()方法，示例

> 原文:[https://www.geeksforgeeks.org/enummap-clear-method-in-java/](https://www.geeksforgeeks.org/enummap-clear-method-in-java/)

Java 中的 Java.util.EnumMap.clear()方法用于从映射中移除所有映射。该方法不删除映射，而是清除映射的映射。

**语法:**

```
enum_map.clear()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

下面的程序说明了 Java.util.EnumMap.clear()方法的工作:
**程序 1:**

```
// Java program to demonstrate clear() method
import java.util.*;

// An enum of geeksforgeeks ranking across
// Worldwide & in India is created
public enum gfg {
    Global,
    India
}
;

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp = new EnumMap<gfg, Integer>(gfg.class);

        // Values are associated in mp
        mp.put(gfg.Global, 800);
        mp.put(gfg.India, 72);

        // Values in mp before removing
        System.out.println("Values in map before removing " + mp);

        // Removing the values from mp
        mp.clear();

        // Values in mp after removing
        System.out.println("Values in map after removing " + mp);
    }
}
```

**Output:**

```
Values in map before removing {Global=800, India=72}
Values in map after removing {}

```

**程序 2:**

```
// Java program to demonstrate clear() method
import java.util.*;

// An enum of fruits price is created
public enum Price_of_Fruits {
    Orange,
    Apple,
    Banana,
    Pomegranate,
    Guava

}
;

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<Price_of_Fruits, Integer> mp = new EnumMap<Price_of_Fruits, Integer>(Price_of_Fruits.class);

        // Values are associated in mp
        mp.put(Price_of_Fruits.Orange, 30);
        mp.put(Price_of_Fruits.Apple, 50);
        mp.put(Price_of_Fruits.Banana, 40);
        mp.put(Price_of_Fruits.Pomegranate, 120);
        mp.put(Price_of_Fruits.Guava, 20);

        // Values in mp before removing
        System.out.println("Values in map before removing " + mp);

        // Removing the values from mp
        mp.clear();

        // Values in mp after removing
        System.out.println("Values in map after removing " + mp);
    }
}
```

**Output:**

```
Values in map before removing {Orange=30, Apple=50, Banana=40, 
                                    Pomegranate=120, Guava=20}
Values in map after removing {}

```