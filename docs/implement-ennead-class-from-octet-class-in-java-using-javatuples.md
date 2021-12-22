# 使用 JavaTuples

从 Java 中的八位字节类实现 Ennead 类

> 原文:[https://www . geesforgeks . org/implement-ennead-class-from-octet-class-in-Java-using-javatuples/](https://www.geeksforgeeks.org/implement-ennead-class-from-octet-class-in-java-using-javatuples/)

**先决条件:**T2【恩内班】[八位体班](https://www.geeksforgeeks.org/octet-class-in-java-tuples/)

以下是在 Java 中使用八位字节类实现 Ennead 类的方法:

1.  **Using direct values**

    ```
    // Java program to illustrate
    // implementing Ennead Class 
    // from Octet Class 
    // using direct values

    import java.util.*;
    import org.javatuples.*;

    class GfG {

        public static void main(String[] args)
        {
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead",
                    octet.getValue0(),
                    octet.getValue1(),
                    octet.getValue2(),
                    octet.getValue3(),
                    octet.getValue4(),
                    octet.getValue5(),
                    octet.getValue6(),
                    octet.getValue7());

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

2.  **Using Octet.add() method**

    ```
    // Java program to illustrate
    // implementing Ennead Class 
    // from Octet Class 
    // using Octet.add()

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.add("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit, Ennead]

    ```

3.  **Using Octet.addAtX() method**

    **程序 1:** 使用 addAt0()在位置 0 添加

    ```
    // Java program to illustrate
    // implementing Ennead Class 
    // from Octet Class 
    // using addAtx()

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
           // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.addAt0("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Ennead, Octet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

    **程序 2:** 使用 addAt1()在位置 1 添加

    ```
    // Java program to illustrate
    // implementing Ennead Class 
    // from Octet Class 
    // using addAt1()

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.addAt1("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Octet, Ennead, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

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
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.addAt2("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Octet, Septet, Ennead, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

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
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.addAt3("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Octet, Septet, Sextet, Ennead, Quintet, Quartet, Triplet, Pair, Unit]

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
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.addAt4("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Octet, Septet, Sextet, Quintet, Ennead, Quartet, Triplet, Pair, Unit]

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
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.addAt5("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Octet, Septet, Sextet, Quintet, Quartet, Ennead, Triplet, Pair, Unit]

    ```

    **程序 7:** 使用 addAt6()在位置 6 添加

    ```
    // Below is a Java program to demonstrate
    // use of addAt6() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

       class GfG {
        public static void main(String[] args)
        {
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.addAt6("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Ennead, Pair, Unit]

    ```

    **程序 8:** 使用 addAt7()在位置 7 添加

    ```
    // Below is a Java program to demonstrate
    // use of addAt7() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

       class GfG {
        public static void main(String[] args)
        {
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.addAt7("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Ennead, Unit]

    ```

    **程序 9:** 使用 addAt8()在位置 8 添加

    ```
    // Below is a Java program to demonstrate
    // use of addAt8() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

       class GfG {
        public static void main(String[] args)
        {
            // Create Octet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Octet
            System.out.println("Octet: " + octet);

            // Create Ennead from Octet
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = octet.addAt8("Ennead");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);
        }
    }
    ```

    **输出:**

    ```
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Ennead: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit, Ennead]

    ```