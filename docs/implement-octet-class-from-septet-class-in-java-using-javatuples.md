# 使用 JavaTuples

在 Java 中实现来自 Septet 类的八位字节类

> 原文:[https://www . geesforgeks . org/implement-octet-class-from-sept-class-in-Java-using-javatuples/](https://www.geeksforgeeks.org/implement-octet-class-from-septet-class-in-java-using-javatuples/)

**先决条件:**T2【八位字节类】[九位字节类](https://www.geeksforgeeks.org/septet-class-in-java-tuples/)

下面是在 Java 中使用七进制类实现八进制类的方法:

1.  **Using direct values**

    ```java
    // Java program to illustrate
    // implementing Octet Class 
    // from Septet Class 
    // using direct values

    import java.util.*;
    import org.javatuples.*;

    class GfG {

        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = new Octet<String, String, String, String, String, String, String, String>(
                    "Octet",
                    septet.getValue0(),
                    septet.getValue1(),
                    septet.getValue2(),
                    septet.getValue3(),
                    septet.getValue4(),
                    septet.getValue5(),
                    septet.getValue6());

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

2.  **Using Septet.add() method**

    ```java
    // Java program to illustrate
    // implementing Octet Class 
    // from Septet Class 
    // using Septet.add()

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = septet.add("Octet");

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit, Octet]

    ```

3.  **Using Septet.addAtX() method**

    **程序 1:** 使用 addAt0()在位置 0 添加

    ```java
    // Java program to illustrate
    // implementing Octet Class 
    // from Septet Class 
    // using Septet.addAtX()

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = septet.addAt0("Octet");

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

    **程序 2:** 使用 addAt1()在位置 1 添加

    ```java
    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = septet.addAt1("Octet");

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Septet, Octet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

    **程序 3:** 使用 addAt2()在位置 2 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt2() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = septet.addAt2("Octet");

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Septet, Sextet, Octet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

    **程序 4:** 使用 addAt3()在位置 3 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt3() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = septet.addAt3("Octet");

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Septet, Sextet, Quintet, Octet, Quartet, Triplet, Pair, Unit]

    ```

    **程序 5:** 使用 addAt4()在位置 4 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt4() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

       class GfG {
        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = septet.addAt4("Octet");

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Septet, Sextet, Quintet, Quartet, Octet, Triplet, Pair, Unit]

    ```

    **程序 6:** 使用 addAt5()在位置 5 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt5() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = septet.addAt5("Octet");

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Septet, Sextet, Quintet, Quartet, Triplet, Octet, Pair, Unit]

    ```

    **程序 7:** 使用 addAt6()在位置 6 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt6() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

       class GfG {
        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = septet.addAt6("Octet");

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Octet, Unit]

    ```

    **程序 8:** 使用 addAt6()在位置 7 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt7() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

       class GfG {
        public static void main(String[] args)
        {
            // Create Septet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Septet
            System.out.println("Septet: " + septet);

            // Create Octet from Septet
            Octet<String, String, String, String, String, String, String, String>
                octet = septet.addAt7("Octet");

            // Print the Octet
            System.out.println("Octet: " + octet);
        }
    }
    ```

    **输出:**

    ```java
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Octet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit, Octet]

    ```