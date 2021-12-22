# 枚举等于()Java 中的方法，示例

> 原文:[https://www . geesforgeks . org/enummap-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/enummap-equals-method-in-java-with-examples/)

Java 中的 Java . util . EnumMap . equals(*obj*)用于将传递的对象与**这个 EnumMap** 进行比较，以获得相等性。必须记住，传递的对象必须是与 EnumMap 类型相同的映射。
**语法:**

```java
boolean equals(Object obj)
```

**参数:**该方法取一个对象类型的参数*对象*，并参照该地图与该地图进行比较。
**返回值:**如果指定对象等于地图，则方法返回 true 否则返回 false。
以下程序说明了 equals()方法的工作:
**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate equals() method
import java.util.*;

// An enum of gfg ranking worldwide and in India
public enum gfg {
    Global_2018,
    India_2018,
    China_2018
}
;

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp1 = new EnumMap<gfg, Integer>(gfg.class);

        EnumMap<gfg, Integer> mp2 = new EnumMap<gfg, Integer>(gfg.class);

        // Values are associated in mp1
        mp1.put(gfg.Global_2018, 800);
        mp1.put(gfg.India_2018, 72);

        // Values are associated in mp2
        mp2.put(gfg.Global_2018, 800);
        mp2.put(gfg.India_2018, 72);

        // Stores the result
        boolean res1 = mp1.equals(mp2);

        // Prints the result
        System.out.println("Map1 equal to Map2: " + res1);

        mp2.put(gfg.China_2018, 1607);

        // Stores the result
        boolean res2 = mp1.equals(mp2);

        // Prints the result
        System.out.println("Map1 equal to Map2: " + res2);
    }
}
```

**Output:** 

```java
Map1 equal to Map2: true
Map1 equal to Map2: false
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate equals() method
import java.util.*;

// an enum of gdp growth rate
// in recent years of India
public enum gdp {
    Ind_2015,
    Ind_2016,
    Ind_2017,
    Ind_2018,
    Ind_2019
}
;

class Enum_map {
    public static void main(String[] args)
    {

        EnumMap<gdp, String> mp1 = new EnumMap<gdp, String>(gdp.class);

        EnumMap<gdp, String> mp2 = new EnumMap<gdp, String>(gdp.class);

        // Values are associated in mp1
        mp1.put(gdp.Ind_2015, "8.4");
        mp1.put(gdp.Ind_2016, "9.2");
        mp1.put(gdp.Ind_2017, "6.1");
        mp1.put(gdp.Ind_2018, "7.7");

        // Values are associated in mp2
        mp2.put(gdp.Ind_2015, "8.4");
        mp2.put(gdp.Ind_2016, "9.2");
        mp2.put(gdp.Ind_2017, "6.1");
        mp2.put(gdp.Ind_2018, "7.7");

        // Stores the result
        boolean res1 = mp1.equals(mp2);

        // Prints the result
        System.out.println("Map1 equal to Map2: " + res1);

        mp2.put(gdp.Ind_2019, "7.0");

        // Stores the result
        boolean res2 = mp1.equals(mp2);

        // Prints the result
        System.out.println("Map1 equal to Map2: " + res2);
    }
}
```

**Output:** 

```java
Map1 equal to Map2: true
Map1 equal to Map2: false
```