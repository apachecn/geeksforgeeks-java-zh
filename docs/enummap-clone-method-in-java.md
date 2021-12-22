# Java 中的 EnumMap 克隆()方法

> 原文:[https://www.geeksforgeeks.org/enummap-clone-method-in-java/](https://www.geeksforgeeks.org/enummap-clone-method-in-java/)

Java 中的 Java.util.EnumMap.clone()方法用于将一个映射的值复制到另一个映射。它基本上创建了这张地图的一个浅拷贝。

**语法:**

```
Enum_map_2 = Enum_map_1.clone()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回一个枚举的浅拷贝。

下面的程序说明了 Java.util.EnumMap.clone()方法

**程序 1:**

```
// Java program to demonstrate clone() method
import java.util.*;

// An enum of fruits price is created
public enum Price_of_Fruits {
    Orange,
    Apple,
    Banana,
    Pomegranate,
    Guava
};

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<Price_of_Fruits, Integer> mp1 = new EnumMap<Price_of_Fruits,
                                             Integer>(Price_of_Fruits.class);

        EnumMap<Price_of_Fruits, Integer> mp2 = new EnumMap<Price_of_Fruits, 
                                             Integer>(Price_of_Fruits.class);

        // Values are associated in mp1
        mp1.put(Price_of_Fruits.Orange, 30);
        mp1.put(Price_of_Fruits.Apple, 60);
        mp1.put(Price_of_Fruits.Banana, 40);
        mp1.put(Price_of_Fruits.Pomegranate, 120);
        mp1.put(Price_of_Fruits.Guava, 20);

        // Price of fruits in mp1
        System.out.println("Price of fruits in 1st map " + mp1);

        // Copying the values of mp1 to mp2
        mp2 = mp1.clone();

        // Price of fruits in mp2
        System.out.println("Price of fruits in 2nd map " + mp2);
    }
}
```

**Output:**

```
Price of fruits in 1st map {Orange=30, Apple=60, Banana=40, Pomegranate=120, Guava=20}
Price of fruits in 2nd map {Orange=30, Apple=60, Banana=40, Pomegranate=120, Guava=20}

```

**程序 2:**

```
// Java program to demonstrate clone() method
import java.util.*;

// An enum of gfg ranking is created
public enum gfg_ranking {
    Global_2018,
    India_2018
};

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<gfg_ranking, Integer> mp1 = new EnumMap<gfg_ranking, 
                                          Integer>(gfg_ranking.class);

        EnumMap<gfg_ranking, Integer> mp2 = new EnumMap<gfg_ranking,
                                          Integer>(gfg_ranking.class);

        // Values are associated in mp1
        mp1.put(gfg_ranking.Global_2018, 800);
        mp1.put(gfg_ranking.India_2018, 72);

        // Price of fruits in mp1
        System.out.println("GeeksforGeeks ranking in first map " + mp1);

        // Copying the values of mp1 to mp2
        mp2 = mp1.clone();

        // Price of fruits in mp2
        System.out.println("GeeksforGeeks ranking in second map " + mp2);
    }
}
```

**Output:**

```
GeeksforGeeks ranking in first map {Global_2018=800, India_2018=72}
GeeksforGeeks ranking in second map {Global_2018=800, India_2018=72}

```