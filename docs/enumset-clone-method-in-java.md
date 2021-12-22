# Java 中的枚举克隆()方法

> 原文:[https://www.geeksforgeeks.org/enumset-clone-method-in-java/](https://www.geeksforgeeks.org/enumset-clone-method-in-java/)

Java 中的 Java.util.EnumSet.clone()方法用于返回现有集合或此集合的浅层副本。

**语法:**

```
Enum_Set_2 = Enum_Set_1.clone()
```

**参数:**该方法不取任何参数。

**返回值:**该方法不返回值。

以下程序说明了 Java.util.EnumSet.clone()方法的工作:
**程序 1:**

```
// Java program to demonstrate clone() method
import java.util.*;

// Creating an enum of GFG type
enum GFG {
    Welcome,
    To,
    The,
    World,
    of,
    Geeks
}
;

public class Enum_Set_Demo {

    public static void main(String[] args)
    {

        // Creating an empty EnumSet
        // Getting all elements from GFG
        EnumSet<GFG> e_set = EnumSet.allOf(GFG.class);
        ;

        // Displaying the empty EnumSet
        System.out.println("Initial set: " + e_set);

        // Cloning the set
        EnumSet<GFG> final_set = e_set.clone();

        // Displaying the final set
        System.out.println("The updated set is:" + final_set);
    }
}
```

**Output:**

```
Initial set: [Welcome, To, The, World, of, Geeks]
The updated set is:[Welcome, To, The, World, of, Geeks]

```

**程序 2:**

```
// Java program to demonstrate clone() method
import java.util.*;

// Creating an enum of CARS type
enum CARS {
    RANGE_ROVER,
    MUSTANG,
    CAMARO,
    AUDI,
    BMW
}
;

public class Enum_Set_Demo {

    public static void main(String[] args)
    {

        // Creating an empty EnumSet
        // Getting all elements from CARS
        EnumSet<CARS> e_set = EnumSet.allOf(CARS.class);
        ;

        // Displaying the empty EnumSet
        System.out.println("Initial set: " + e_set);

        // Cloning the set
        EnumSet<CARS> final_set = e_set.clone();

        // Displaying the final set
        System.out.println("The updated set is:" + final_set);
    }
}
```

**Output:**

```
Initial set: [RANGE_ROVER, MUSTANG, CAMARO, AUDI, BMW]
The updated set is:[RANGE_ROVER, MUSTANG, CAMARO, AUDI, BMW]

```