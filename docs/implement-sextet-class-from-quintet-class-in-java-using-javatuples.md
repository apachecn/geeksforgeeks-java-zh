# 使用 JavaTuples

在 Java 中实现五次类中的六次类

> 原文:[https://www . geesforgeks . org/implement-sextet-class-from-quintet-class-in-Java-using-javatuples/](https://www.geeksforgeeks.org/implement-sextet-class-from-quintet-class-in-java-using-javatuples/)

**先决条件:** [六重奏班](https://www.geeksforgeeks.org/sextet-class-in-java-tuples/)[五重奏班](https://www.geeksforgeeks.org/quintet-class-in-java-tuples/)

以下是在 Java 中使用五重奏类实现六重奏类的方法:

1.  **Using direct values**

    ```
    // Java program to illustrate
    // implementing Sextet Class 
    // from Quintet Class using 
    // direct values

    import java.util.*;
    import org.javatuples.*;

    class GfG {

        public static void main(String[] args)
        {
            // create Quintet
            Quintet<String, String, String, String, String>
                quintet = new Quintet<String, String, String, String, String>(
                    "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Quintet
            System.out.println("Quintet: " + quintet);

            // Create Sextet from Quintet
            Sextet<String, String, String, String, String, String>
                sextet = new Sextet<String, String, String, String, String, String>(
                    "Sextet",
                    quintet.getValue0(),
                    quintet.getValue1(),
                    quintet.getValue2(),
                    quintet.getValue3(),
                    quintet.getValue4());

            // Print the Sextet
            System.out.println("Sextet: " + sextet);
        }
    }
    ```

    **输出:**

    ```
    Quintet: [Quintet, Quartet, Triplet, Pair, Unit]
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    ```

2.  **Using Quintet.add() method**

    ```
    // Java program to illustrate
    // implementing Sextet Class 
    // from Quintet Class 
    // using Quintet.add()

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // create Quintet
            Quintet<String, String, String, String, String>
                quintet = new Quintet<String, String, String, String, String>(
                    "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Quintet
            System.out.println("Quintet: " + quintet);

            // Create Sextet from Quintet
            Sextet<String, String, String, String, String, String>
                sextet = quintet.add("Sextet");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);
        }
    }
    ```

    **输出:**

    ```
    Quintet: [Quintet, Quartet, Triplet, Pair, Unit]
    Sextet: [Quintet, Quartet, Triplet, Pair, Unit, Sextet]
    ```

3.  **Using Quintet.addAtX() method**

    **程序 1:** 使用 addAt0()在位置 0 添加

    ```
    // Java program to illustrate
    // implementing Sextet Class 
    // from Quintet Class
    // using addAt(0)

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // create Quintet
            Quintet<String, String, String, String, String>
                quintet = new Quintet<String, String, String, String, String>(
                    "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Quintet
            System.out.println("Quintet: " + quintet);

            // Create Sextet from Quintet
            Sextet<String, String, String, String, String, String>
                sextet = quintet.addAt0("Sextet");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);
        }
    }
    ```

    **输出:**

    ```
    Quintet: [Quintet, Quartet, Triplet, Pair, Unit]
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    ```

    **程序 2:** 使用 addAt1()在位置 1 添加

    ```
    // Java program to illustrate
    // implementing Sextet Class 
    // from Quintet Class 
    // using addAt1()

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // create Quintet
            Quintet<String, String, String, String, String>
                quintet = new Quintet<String, String, String, String, String>(
                    "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Quintet
            System.out.println("Quintet: " + quintet);

            // Using add() to create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = quintet.addAt1("Sextet");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);
        }
    }
    ```

    **输出:**

    ```
    Quintet: [Quintet, Quartet, Triplet, Pair, Unit]
    Sextet: [Quintet, Sextet, Quartet, Triplet, Pair, Unit]
    ```

    **程序 3:** 使用 addAt2()在位置 2 添加

    ```
    // Below is a Java program to demonstrate
    // use of addAt2() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // create Quintet
            Quintet<String, String, String, String, String>
                quintet = new Quintet<String, String, String, String, String>(
                    "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Quintet
            System.out.println("Quintet: " + quintet);

            // Using add() to create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = quintet.addAt2("Sextet");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);
        }
    }
    ```

    **输出:**

    ```
    Quintet: [Quintet, Quartet, Triplet, Pair, Unit]
    Sextet: [Quintet, Quartet, Sextet, Triplet, Pair, Unit]
    ```

    **程序 4:** 使用 addAt3()在位置 3 添加

    ```
    // Below is a Java program to demonstrate
    // use of addAt3() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // create Quintet
            Quintet<String, String, String, String, String>
                quintet = new Quintet<String, String, String, String, String>(
                    "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Quintet
            System.out.println("Quintet: " + quintet);

            // Using add() to create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = quintet.addAt3("Sextet");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);
        }
    }
    ```

    **输出:**

    ```
    Quintet: [Quintet, Quartet, Triplet, Pair, Unit]
    Sextet: [Quintet, Quartet, Triplet, Sextet, Pair, Unit]
    ```

    **程序 5:** 使用 addAt4()在位置 4 添加

    ```
    // Below is a Java program to demonstrate
    // use of addAt4() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // create Quintet
            Quintet<String, String, String, String, String>
                quintet = new Quintet<String, String, String, String, String>(
                    "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Quintet
            System.out.println("Quintet: " + quintet);

            // Using add() to create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = quintet.addAt4("Sextet");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);
        }
    }
    ```

    **输出:**

    ```
    Quintet: [Quintet, Quartet, Triplet, Pair, Unit]
    Sextet: [Quintet, Quartet, Triplet, Pair, Sextet, Unit]
    ```

    **程序 6:** 使用 addAt5()在位置 5 添加

    ```
    // Below is a Java program to demonstrate
    // use of addAt5() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // create Quintet
            Quintet<String, String, String, String, String>
                quintet = new Quintet<String, String, String, String, String>(
                    "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Quintet
            System.out.println("Quintet: " + quintet);

            // Using add() to create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = quintet.addAt5("Sextet");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);
        }
    }
    ```

    **输出:**

    ```
    Quintet: [Quintet, Quartet, Triplet, Pair, Unit]
    Sextet: [Quintet, Quartet, Triplet, Pair, Unit, Sextet]
    ```