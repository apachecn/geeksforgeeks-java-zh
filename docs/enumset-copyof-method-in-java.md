# Java 中枚举 copyOf()方法

> 原文:[https://www . geesforgeks . org/enumset-copy of-in-method-in-Java/](https://www.geeksforgeeks.org/enumset-copyof-method-in-java/)

1.  **The java.util.EnumSet.copyOf(*Collection collect*)** method in Java is used to copy all of the contents from a collection to a new enum set. At first, the collection is made out of the elements of the enum and then a new enum set is created, which is the copy of the collection.

    **语法:**

    ```
    New_Enum_Set = EnumSet.copyOf(*Collection collect*)
    ```

    **参数:**该方法接受枚举的对象类型的一个参数*集合*，并引用其值将被复制到 New_Enum_Set 中的集合。

    **返回值:**该方法不返回值。

    **异常:**

    *   *IllegalArgumentException* :如果 *collect* 不是枚举实例，并且包含无法与枚举进行比较的元素或者不包含元素，则会引发此异常。
    *   *空指针异常*:如果*收集*为空，则抛出该异常。

    下面的程序说明了 java.util.EnumSet.copyOf()方法的工作原理:

    ```
    // Java program to demonstrate copyOf() method
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

            // Creating an empty collection
            Collection<GFG> collect = new ArrayList<GFG>();

            // Adding elements to the Collection
            collect.add(GFG.Welcome);
            collect.add(GFG.World);
            collect.add(GFG.Geeks);

            // Displaying the collection
            System.out.println("The collection is: " + collect);

            EnumSet<GFG> e_set = EnumSet.copyOf(collect);

            // Displaying the final set
            System.out.println("The enum set is:" + e_set);
        }
    }
    ```

    **Output:**

    ```
    The collection is: [Welcome, World, Geeks]
    The enum set is:[Welcome, World, Geeks]

    ```

2.  The **java.util.EnumSet.copyOf(*EnumSet e_set*)** method in Java is used to copy all of the contents from an existing EnumSet i.e., e_set, to a new enum set.

    **语法:**

    ```
    New_Enum_Set = EnumSet.copyOf(*EnumSet e_set*)
    ```

    **参数:**该方法接受枚举的对象类型的一个参数 *e_set* ，并引用其值将被复制到 New_Enum_Set 中的集合。

    **返回值:**该方法不返回值。

    **异常:**当 *e_set* 为空时，该方法抛出*空指针异常*。

    下面的程序说明了 java.util.EnumSet.copyOf()方法的工作原理:

    ```
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
            System.out.println("Initial set is: " + e_set);

            // Copying the set
            EnumSet<CARS> new_set = EnumSet.copyOf(e_set);

            // Displaying the final set
            System.out.println("The new set is: " + new_set);
        }
    }
    ```

    **Output:**

    ```
    Initial set is: [RANGE_ROVER, MUSTANG, CAMARO, AUDI, BMW]
    The new set is: [RANGE_ROVER, MUSTANG, CAMARO, AUDI, BMW]

    ```