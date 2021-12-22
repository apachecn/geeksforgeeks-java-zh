# 使用 JavaTuples

在 Java 中用四重奏类实现五重奏类

> 原文:[https://www . geesforgeks . org/implement-quintet-class-with-quartet-class-in-Java-use-Java-tuples/](https://www.geeksforgeeks.org/implement-quintet-class-with-quartet-class-in-java-using-java-tuples/)

以下是用[四重奏类](https://www.geeksforgeeks.org/quartet-class-in-java-tuples/)实现[五重奏类](https://www.geeksforgeeks.org/quintet-class-in-java-tuples/)的方法

1.  **Using direct values**

    ```
    import java.util.*;
    import org.javatuples.*;

    class GfG {

        public static void main(String[] args)
        {
            // create Quartet
            Quartet<String, String, String, String>
                quartet = new Quartet<String, String, String, String>(
                    "Quartet", "Triplet", "Pair", "Unit");

            // Print Quartet
            System.out.println("Quartet: " + quartet);

            // Create Quintet from Quartet
            Quintet<String, String, String, String, String>
                quintet = new Quintet<String, String, String, String, String>(
                    "Quintet 1",
                    quartet.getValue0(),
                    quartet.getValue1(),
                    quartet.getValue2(),
                    quartet.getValue3());

            // Print Quintet
            System.out.println("Quintet: " + quintet);
        }
    }
    ```

    **输出:**

    ```
    [Quintet, Triplet 1, 1, GeeksforGeeks]
    [Quintet 1, Quintet, Triplet 1, 1, GeeksforGeeks]
    ```

2.  **Using Quartet.add() method**

    ```
    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // create Quartet
            Quartet<String, String, String, String>
                quartet = new Quartet<String, String, String, String>(
                    "Quartet", "Triplet", "Pair", "Unit");

            // Print Quartet
            System.out.println("Quartet: " + quartet);

            // Create Quintet from Quartet
            Quintet<String, String, String, String, String>
                quintet = quartet.add("Quintet");

            // Print Quintet
            System.out.println("Quintet: " + quintet);
        }
    }
    ```

    **输出:**

    ```
    Quartet: [Quartet, Triplet, Pair, Unit]
    Quintet: [Quartet, Triplet, Pair, Unit, Quintet]
    ```

3.  **Using Quartet.addAtX() method**

    **程序 1:** 使用 addAt0()在位置 0 添加

    ```
    // Below is a Java program to demonstrate
    // use of addAt0() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // create Quartet
            Quartet<String, String, String, String>
                quartet = new Quartet<String, String, String, String>(
                    "Quartet", "Triplet", "Pair", "Unit");

            // Print Quartet
            System.out.println("Quartet: " + quartet);

            // Create Quintet from Quartet
            Quintet<String, String, String, String, String>
                quintet = quartet.addAt0("Quintet");

            // Print Quintet
            System.out.println("Quintet: " + quintet);
        }
    }
    ```

    **输出:**

    ```
    Quartet: [Quartet, Triplet, Pair, Unit]
    Quintet: [Quintet, Quartet, Triplet, Pair, Unit]
    ```

    **程序 2:** 使用 addAt1()在位置 1 添加

    ```
    // Below is a Java program to demonstrate
    // use of addAt1() method with
    // direct value

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // create Quartet
            Quartet<String, String, String, String>
                quartet = new Quartet<String, String, String, String>(
                    "Quartet", "Triplet", "Pair", "Unit");

            // Print Quartet
            System.out.println("Quartet: " + quartet);

            // Create Quintet from Quartet
            Quintet<String, String, String, String, String>
                quintet = quartet.addAt1("Quintet");

            // Print Quintet
            System.out.println("Quintet: " + quintet);
        }
    }
    ```

    **输出:**

    ```
    Quartet: [Quartet, Triplet, Pair, Unit]
    Quintet: [Quartet, Quintet, Triplet, Pair, Unit]
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
            // create Quartet
            Quartet<String, String, String, String>
                quartet = new Quartet<String, String, String, String>(
                    "Quartet", "Triplet", "Pair", "Unit");

            // Print Quartet
            System.out.println("Quartet: " + quartet);

            // Create Quintet from Quartet
            Quintet<String, String, String, String, String>
                quintet = quartet.addAt2("Quintet");

            // Print Quintet
            System.out.println("Quintet: " + quintet);
        }
    }
    ```

    **输出:**

    ```
    Quartet: [Quartet, Triplet, Pair, Unit]
    Quintet: [Quartet, Triplet, Quintet, Pair, Unit]
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
            // create Quartet
            Quartet<String, String, String, String>
                quartet = new Quartet<String, String, String, String>(
                    "Quartet", "Triplet", "Pair", "Unit");

            // Print Quartet
            System.out.println("Quartet: " + quartet);

            // Create Quintet from Quartet
            Quintet<String, String, String, String, String>
                quintet = quartet.addAt3("Quintet");

            // Print Quintet
            System.out.println("Quintet: " + quintet);
        }
    }
    ```

    **输出:**

    ```
    Quartet: [Quartet, Triplet, Pair, Unit]
    Quintet: [Quartet, Triplet, Pair, Quintet, Unit]
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
            // create Quartet
            Quartet<String, String, String, String>
                quartet = new Quartet<String, String, String, String>(
                    "Quartet", "Triplet", "Pair", "Unit");

            // Print Quartet
            System.out.println("Quartet: " + quartet);

            // Create Quintet from Quartet
            Quintet<String, String, String, String, String>
                quintet = quartet.addAt4("Quintet");

            // Print Quintet
            System.out.println("Quintet: " + quintet);
        }
    }
    ```

    **输出:**

    ```
    Quartet: [Quartet, Triplet, Pair, Unit]
    Quintet: [Quartet, Triplet, Pair, Unit, Quintet]
    ```