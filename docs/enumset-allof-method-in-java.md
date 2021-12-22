# Java 中的枚举 allof()方法

> 原文:[https://www.geeksforgeeks.org/enumset-allof-method-in-java/](https://www.geeksforgeeks.org/enumset-allof-method-in-java/)

Java 中的 Java.util.EnumSet.allOf( *类 <e>elementType</e>* )用于创建枚举集，该枚举集将用于包含指定的 *elementType* 中的所有元素。

**语法:**

```java
public static > EnumSet <e>allOf(*Class <e>elementType</e>*)</e>
```

**参数:**该方法接受一个元素类型的参数*元素类型*，并引用其元素要存储到集合中的类对象。

**返回值:**该方法不返回值。

**异常:**如果*元素类型*为空，该方法抛出*空指针异常*。

下面的程序说明了 Java.util.EnumSet.allOf()方法的工作:
**程序 1:**

```java
// Java program to demonstrate allof() method
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
        EnumSet<GFG> e_set = null;

        // Displaying the empty EnumSet
        System.out.println(e_set);

        // Getting all elements from GFG
        e_set = EnumSet.allOf(GFG.class);

        // Displaying the final set
        System.out.println("The updated set is:" + e_set);
    }
}
```

**Output:**

```java
null
The updated set is:[Welcome, To, The, World, of, Geeks]

```

**程序 2:**

```java
// Java program to demonstrate allof() method
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
        EnumSet<CARS> e_set = null;

        // Displaying the empty EnumSet
        System.out.println(e_set);

        // Getting all elements from CARS
        e_set = EnumSet.allOf(CARS.class);

        // Displaying the final set
        System.out.println("The updated set is:" + e_set);
    }
}
```

**Output:**

```java
null
The updated set is:[RANGE_ROVER, MUSTANG, CAMARO, AUDI, BMW]

```