# Java 中()方法的枚举

> 原文:[https://www.geeksforgeeks.org/enumset-of-method-in-java/](https://www.geeksforgeeks.org/enumset-of-method-in-java/)

1.  The **java.util.EnumSet.of(E ele1, E ele2, E ele3, …)** method in Java is used to create an enum set initially containing the specified elements in the parameters. When multiple items are added at the same time the elements are pushed down the set as the new elements are added. When different elements are added at different time or iteration, the old elements get replaced.

    **语法:**

    ```java
    Enum_Set = EnumSet.of(*E ele1, E ele2, E ele3, ...*)
    ```

    **参数:**该方法可以获取枚举中存在的多个参数。

    **返回值:**该方法返回一个枚举集，该枚举集最初包含通过参数传递的指定元素。

    **异常:**如果传递的任何元素为空，该方法将引发 NullPointerException。

    下面的程序说明了()方法的工作原理:
    **程序 1:** 一次添加一个元素会替换上一个元素。

    ```java
    // Java program to demonstrate range() method
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

            // Creating an EnumSet
            EnumSet<GFG> e_set;

            // Adding elements
            e_set = EnumSet.of(GFG.The);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);

            // Adding elements
            e_set = EnumSet.of(GFG.Geeks);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);

            // Adding elements
            e_set = EnumSet.of(GFG.Welcome);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);
        }
    }
    ```

    **Output:**

    ```java
    The enum set is: [The]
    The enum set is: [Geeks]
    The enum set is: [Welcome]

    ```

    **程序 2:** 同时添加两个元素。

    ```java
    // Java program to demonstrate range() method
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

            // Creating an EnumSet
            EnumSet<GFG> e_set;

            // Adding elements
            e_set = EnumSet.of(GFG.The, GFG.Geeks);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);

            // Adding elements
            e_set = EnumSet.of(GFG.Geeks, GFG.Welcome);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);

            // Adding elements
            e_set = EnumSet.of(GFG.of, GFG.World);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);
        }
    }
    ```

    **Output:**

    ```java
    The enum set is: [The, Geeks]
    The enum set is: [Welcome, Geeks]
    The enum set is: [World, of]

    ```

    **程序 3:** 同时添加多个元素。

    ```java
    // Java program to demonstrate range() method
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

            // Creating an EnumSet
            EnumSet<GFG> e_set;

            // Adding 2 elements
            e_set = EnumSet.of(GFG.The, GFG.Geeks);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);

            // Adding 3 elements
            e_set = EnumSet.of(GFG.The, GFG.Geeks, GFG.Welcome);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);

            // Adding 4 elements
            e_set = EnumSet.of(GFG.Geeks, GFG.Welcome,
                               GFG.of, GFG.World);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);

            // Adding 5 elements
            e_set = EnumSet.of(GFG.Welcome, GFG.To, GFG.The,
                               GFG.of, GFG.World, GFG.Geeks);

            // Displaying the updated set
            System.out.println("The enum set is: " + e_set);
        }
    }
    ```

    **Output:**

    ```java
    The enum set is: [The, Geeks]
    The enum set is: [Welcome, The, Geeks]
    The enum set is: [Welcome, World, of, Geeks]
    The enum set is: [Welcome, To, The, World, of, Geeks]

    ```

2.  The **java.util.EnumSet.of(*E_first, E_rest*)** is used to create an enum set initially containing all the specified elements. This factory, whose parameter list uses the var_args feature, can also be used to create an enum set initially containing an arbitrary number of elements, but it comes with a disadvantage of making the program to run slower than the overloadings that do not use var_args.
    **Syntax:**

    ```java
    public static <E extends Enum<E>> EnumSet<E> of(E_first, E_rest)
    ```

    **参数:**该方法取两个参数:

    *   *E_first:* 这是枚举类型，指集合最初要包含的元素。
    *   *E_rest:* 这也是枚举类型，指集合最初需要包含的其余元素。

    **返回值:**该方法返回一个枚举集，该枚举集最初包含通过参数传递的指定元素。

    **异常:**如果传递的任何元素为空，该方法将引发 NullPointerException。

    下面的程序说明了( *E_first，E_rest* )方法的工作原理:

    ```java
    // Java program to demonstrate of() method
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

       public static void main(String[] args) {

          // Creating the ist that will be used as args
          GFG[] listing = {GFG.Welcome, GFG.The, 
                           GFG.World, GFG.Geeks};

          // Calling the other main function
          other_main(listing);
       }

       // The other_main.
       public static void other_main(GFG[] other_args) {

          // Creating the set
          EnumSet<GFG> e_set;

          // Adding the first element and the other_args
          e_set = EnumSet.of(GFG.Welcome, other_args);

          // Displaying the e_set
          System.out.println("Set: " + e_set);
       }
    }
    ```

    **Output:**

    ```java
    Set: [Welcome, The, World, Geeks]

    ```