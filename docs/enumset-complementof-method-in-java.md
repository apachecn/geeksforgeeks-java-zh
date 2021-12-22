# Java 中()方法的枚举补充

> 原文:[https://www . geesforgeks . org/enumset-complement of-method-in-Java/](https://www.geeksforgeeks.org/enumset-complementof-method-in-java/)

Java . util . EnumSet . complementof(*Enum_Set*)方法用于创建包含与指定 Enum_Set 类型相同的元素的 EnumSet，这些元素的值存在于枚举中，但不包含在指定 Enum _ Set 中。

**语法:**

```java
New_Enum_Set = EnumSet.complementOf(*Enum_Set*)
```

**参数:**该方法接受一个参数*枚举集*，其值在将值填充到新的补充枚举集中时将被忽略。

**返回值:**该方法不返回值。

**异常:**如果值*枚举 _ 设置*为空，则该方法抛出*空指针异常*。

以下程序说明了()方法的工作原理:
**程序 1:**

```java
// Java program to demonstrate complementOf() method
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
        // Getting elements from GFG
        EnumSet<GFG> e_set = EnumSet.of(GFG.To, GFG.Welcome,
                                        GFG.Geeks);

        // Displaying the empty EnumSet
        System.out.println("Initial set: " + e_set);

        // Cloning the set
        EnumSet<GFG> final_set = EnumSet.complementOf(e_set);

        // Displaying the final set
        System.out.println("The updated set is:" + final_set);
    }
}
```

**Output:**

```java
Initial set: [Welcome, To, Geeks]
The updated set is:[The, World, of]

```

**程序 2:**

```java
// Java program to demonstrate complementOf() method
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

        // Displaying the empty EnumSet
        System.out.println("Initial set: " + e_set);

        // Cloning the set
        EnumSet<CARS> final_set = EnumSet.complementOf(e_set);

        // Displaying the final set
        System.out.println("The updated set is:" + final_set);
    }
}
```

**Output:**

```java
Initial set: [RANGE_ROVER, MUSTANG, CAMARO, AUDI, BMW]
The updated set is:[]

```