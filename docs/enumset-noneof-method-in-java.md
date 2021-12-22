# Java 中的枚举 noneOf()方法

> 原文:[https://www . geesforgeks . org/enumset-none-of-in-method-Java/](https://www.geeksforgeeks.org/enumset-noneof-method-in-java/)

java 中的 java.util.EnumSet.noneOf( *类 <e>elementType</e>* )方法用于创建类型为 *elementType* 的空集合。

**语法:**

```java
public static <E extends Enum<E>> EnumSet<E> noneOf(*Class<E> elementType*)
```

**参数:**该方法接受一个元素类型的参数*元素类型*，并引用该枚举集的元素类型的类对象。

**返回值:**该方法不返回值。

**异常:**如果*元素类型*为空，该方法抛出*空指针异常*。

下面的程序说明了 Java.util.EnumSet.noneOf()方法的工作:
**程序 1:**

```java
// Java program to demonstrate noneof() method
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

        // Displaying the initial EnumSet
        System.out.println("The first set is: " + e_set);

        // Creating another empty set
        EnumSet<GFG> other_set = EnumSet.noneOf(GFG.class);

        // Displaying the new set
        System.out.println("The other set is: " + other_set);
    }
}
```

**Output:**

```java
The first set is: [Welcome, To, The, World, of, Geeks]
The other set is: []

```

**程序 2:**

```java
// Java program to demonstrate copyOf() method
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

        // Displaying the initial EnumSet
        System.out.println("The first set is: " + e_set);

        // Creating another empty set
        EnumSet<CARS> other_set = EnumSet.noneOf(CARS.class);

        // Displaying the new set
        System.out.println("The other set is: " + other_set);
    }
}
```

**Output:**

```java
The first set is: [RANGE_ROVER, MUSTANG, CAMARO, AUDI, BMW]
The other set is: []

```