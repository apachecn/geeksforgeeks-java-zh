# 使用 JavaTuples

在 Java 中实现与单元类的配对类

> 原文:[https://www . geesforgeks . org/implement-pair-class-with-unit-class-in-Java-using-javatuples/](https://www.geeksforgeeks.org/implement-pair-class-with-unit-class-in-java-using-javatuples/)

以下是[结对类](https://www.geeksforgeeks.org/pair-class-in-java-tuples/)和[单元类](https://www.geeksforgeeks.org/unit-class-in-java-tuples/)的实现方式

1.  **Using direct values**

    ```java
    import java.util.*;
    import org.javatuples.*;

    class GfG {

        public static void main(String[] args)
        {
            // Create a Unit
            Unit<String> unit = new Unit<String>("GeeksforGeeks");

            // print unit
            System.out.println("Unit: " + unit);

            // create Pair from Unit
            Pair<Integer, String>
                pair = new Pair<Integer, String>(
                    Integer.valueOf(1), unit.getValue0());

            // Print the Pair
            System.out.println("Pair: " + pair);
        }
    }
    ```

    **输出:**

    ```java
    Unit: [GeeksforGeeks]
    Pair: [1, GeeksforGeeks]

    ```

2.  **Using Unit.add() method**

    ```java
    // Below is a Java program to demonstrate
    // use of add() method with
    // single value

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // Using with() method to instantiate unit object
            Unit<String> unit = Unit.with("Geeks");

            // print unit
            System.out.println("Unit: " + unit);

            // Using add() to create Pair
            Pair<String, String> pair = unit.add("forGeeks");

            // Print the Pair
            System.out.println("Pair: " + pair);
        }
    }
    ```

    **输出:**

    ```java
    Unit: [Geeks]
    Pair: [Geeks, forGeeks]

    ```

3.  **使用 Unit.addAtX()方法**
    *   **Program 1:** Adding Unit at Position 0 using addAt0()

        ```java
        // Below is a Java program to demonstrate
        // use of addAt0() method with
        // direct value

        import java.util.*;
        import org.javatuples.Unit;
        import org.javatuples.Pair;

        class GfG {
            public static void main(String[] args)
            {
                // Using with() method to instantiate unit object
                Unit<String> unit = Unit.with("Geeks");

                // print unit
                System.out.println("Unit: " + unit);

                // Using addAtX() to create Pair
                Pair<String, String> pair = unit.addAt0("forGeeks");

                // Print the Pair
                System.out.println("Pair: " + pair);
            }
        }
        ```

        **输出:**

        ```java
        Unit: [Geeks]
        Pair: [forGeeks, Geeks]

        ```

    *   **Program 2:** Adding Unit at Position 1 using addAt1()

        ```java
        // Below is a Java program to demonstrate
        // use of addAt1() method with
        // direct value

        import java.util.*;
        import org.javatuples.Unit;
        import org.javatuples.Pair;

        class GfG {
            public static void main(String[] args)
            {
                // Using with() method to instantiate unit object
                Unit<String> unit = Unit.with("Geeks");

                // print unit
                System.out.println("Unit: " + unit);

                // Using addAtX() to create Pair
                Pair<String, String> pair = unit.addAt1("forGeeks");

                // Print the Pair
                System.out.println("Pair: " + pair);
            }
        }
        ```

        **输出:**

        ```java
        Unit: [Geeks]
        Pair: [Geeks, forGeeks]

        ```