# Java 中的 EnumMap get()方法

> 原文:[https://www.geeksforgeeks.org/enummap-get-method-in-java/](https://www.geeksforgeeks.org/enummap-get-method-in-java/)

Java 中的 Java.util.EnumMap.get( *对象键*)方法用于给出指定键的映射值。

**语法:**

```
get(*Object key*)
```

**参数:**该方法取一个参数*键*，传递该参数返回与之关联的值。

**返回值:**返回关联键映射的值。

下面的程序说明 get()函数的工作原理:

**程序 1:**

```
// Java program to demonstrate get(key)
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {
    Global,
    India
}
;

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, Integer> mp = new 
                     EnumMap<gfg, Integer>(gfg.class);

        // Values are associated
        mp.put(gfg.Global, 800);
        mp.put(gfg.India, 72);

        // Stores the value mapped with the key specified
        int res = mp.get(gfg.India);

        // Prints the result
        System.out.println("GeeksforGeeks ranked in India: " 
                                                    + res);
    }
}
```

**Output:**

```
GeeksforGeeks ranked in India: 72

```

**程序 2:**

```
// Java program to demonstrate get(key)
import java.util.*;

// An enum of geeksforgeeks
public enum gfg {
    India,
    United_States,
    China
}
;

class Enum_demo {
    public static void main(String[] args)
    {

        EnumMap<gfg, String> mp = new 
                  EnumMap<gfg, String>(gfg.class);

        // Values are associated
        mp.put(gfg.India, "61.7%");
        mp.put(gfg.United_States, "18.2%");
        mp.put(gfg.China, "2.5%");

        // Stores the value mapped with the key specified
        String res = mp.get(gfg.United_States);

        // Prints the result
        System.out.println("Visitors in United_States: " 
                                                   + res);
    }
}
```

**Output:**

```
Visitors in United_States: 18.2%

```