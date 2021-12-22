# 使用 JavaTuples 从 Java 的 Ennead 类实现十年类

> 原文:[https://www . geesforgeks . org/implex-decade-class-from-ennead-class-in-Java-using-javatuples/](https://www.geeksforgeeks.org/implement-decade-class-from-ennead-class-in-java-using-javatuples/)

**先决条件:** [十年班](https://www.geeksforgeeks.org/decade-class-in-java-tuples/)[恩内班](https://www.geeksforgeeks.org/ennead-class-in-java-tuples/)

下面是用 Java 中的 Ennead 类实现十年类的方法:

1.  **Using direct values**

    ```java
    // Java program to illustrate
    // implementing Decade Class 
    // from Ennead Class 
    // using direct values

    import java.util.*;
    import org.javatuples.*;

    class GfG {

        public static void main(String[] args)
        {
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = new Decade<String, String, String, String, String, String, String, String, String, String>(
                    "Decade",
                    ennead.getValue0(),
                    ennead.getValue1(),
                    ennead.getValue2(),
                    ennead.getValue3(),
                    ennead.getValue4(),
                    ennead.getValue5(),
                    ennead.getValue6(),
                    ennead.getValue7(),
                    ennead.getValue8());

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Decade, Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

2.  **Using Ennead.add() method**

    ```java
    // Java program to illustrate
    // implementing Decade Class 
    // from Ennead Class 
    // using add() values

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.add("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit, Decade]

    ```

3.  **Using Ennead.addAtX() method**

    **程序 1:** 使用 addAt0()在位置 0 添加

    ```java
    // Java program to illustrate
    // implementing Decade Class 
    // from Ennead Class 
    // using addAt0() values

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
           // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt0("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Decade, Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

    **程序 2:** 使用 addAt1()在位置 1 添加

    ```java
    // Java program to illustrate
    // implementing Decade Class 
    // from Ennead Class 
    // using add()At1

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt1("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Decade, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

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
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt2("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Octet, Decade, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

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
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt3("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Octet, Septet, Decade, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

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
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt4("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Octet, Septet, Sextet, Decade, Quintet, Quartet, Triplet, Pair, Unit]

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
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt5("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Octet, Septet, Sextet, Quintet, Decade, Quartet, Triplet, Pair, Unit]

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
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt6("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Decade, Triplet, Pair, Unit]

    ```

    **程序 8:** 使用 addAt7()在位置 7 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt7() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

       class GfG {
        public static void main(String[] args)
        {
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt7("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Decade, Pair, Unit]

    ```

    **程序 9:** 使用 addAt8()在位置 8 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt8() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

       class GfG {
        public static void main(String[] args)
        {
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt8("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Decade, Unit]

    ```

    **程序 10:** 使用 addAt9()在位置 9 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt9() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

       class GfG {
        public static void main(String[] args)
        {
            // Create Ennead
            Ennead<String, String, String, String, String, String, String, String, String>
                ennead = new Ennead<String, String, String, String, String, String, String, String, String>(
                    "Ennead", "Octet", "Septet", "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Ennead
            System.out.println("Ennead: " + ennead);

            // Create Decade from Ennead
            Decade<String, String, String, String, String, String, String, String, String, String>
                decade = ennead.addAt9("Decade");

            // Print the Decade
            System.out.println("Decade: " + decade);
        }
    }
    ```

    **输出:**

    ```java
    Ennead: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Decade: [Ennead, Octet, Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit, Decade]

    ```