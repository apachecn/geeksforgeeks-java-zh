# 使用 JavaTuples

从 Java 中的六分之一类实现七分之一类

> 原文:[https://www . geeksforgeeks . org/implement-sept-class-from-sextet-class-in-Java-using-javatuples/](https://www.geeksforgeeks.org/implement-septet-class-from-sextet-class-in-java-using-javatuples/)

**先决条件:**T2【九月班】[六月班](https://www.geeksforgeeks.org/sextet-class-in-java-tuples/)

下面是在 Java 中使用六重奏类实现七重奏类的方法:

1.  **Using direct values**

    ```java
    // Java program to illustrate
    // implementing Septet Class 
    // from Sextet Class 
    // using direct values

    import java.util.*;
    import org.javatuples.*;

    class GfG {

        public static void main(String[] args)
        {
            // Create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = new Sextet<String, String, String, String, String, String>(
                    "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);

            // Create Septet from Sextet
            Septet<String, String, String, String, String, String, String>
                septet = new Septet<String, String, String, String, String, String, String>(
                    "Septet",
                    sextet.getValue0(),
                    sextet.getValue1(),
                    sextet.getValue2(),
                    sextet.getValue3(),
                    sextet.getValue4(),
                    sextet.getValue5());

            // Print the Septet
            System.out.println("Septet: " + septet);
        }
    }
    ```

    **输出:**

    ```java
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

2.  **使用 Sextet.add()方法**
    // Java 程序说明
    //实现 Septet 类
    //从 Sextet 类
    //使用 add()

```java
import java.util.*;
import org.javatuples.*;

class GfG {
    public static void main(String[] args)
    {
        // Create Sextet
        Sextet<String, String, String, String, String, String>
            sextet = new Sextet<String, String, String, String, String, String>(
                "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

        // Print the Sextet
        System.out.println("Sextet: " + sextet);

        // Create Septet from Sextet
        Septet<String, String, String, String, String, String, String>
            septet = sextet.add("Septet");

        // Print the Septet
        System.out.println("Septet: " + septet);
    }
}
```

**输出:**

```java
Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
Septet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit, Septet]

```

8.  **Using Sextet.addAtX() method**

    **程序 1:** 使用 addAt0()在位置 0 添加

    ```java
    // Java program to illustrate
    // implementing Septet Class 
    // from Sextet Class 
    // using addAt0()

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // Create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = new Sextet<String, String, String, String, String, String>(
                    "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);

            // Create Septet from Sextet
            Septet<String, String, String, String, String, String, String>
                septet = sextet.addAt0("Septet");

            // Print the Septet
            System.out.println("Septet: " + septet);
        }
    }
    ```

    **输出:**

    ```java
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Septet: [Septet, Sextet, Quintet, Quartet, Triplet, Pair, Unit]

    ```

    **程序 2:** 使用 addAt1()在位置 1 添加

    ```java
    // Java program to illustrate
    // implementing Septet Class 
    // from Sextet Class 
    // using addAt1()

    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // Create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = new Sextet<String, String, String, String, String, String>(
                    "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);

            // Create Septet from Sextet
            Septet<String, String, String, String, String, String, String>
                septet = sextet.addAt1("Septet");

            // Print the Septet
            System.out.println("Septet: " + septet);
        }
    }
    ```

    **输出:**

    ```java
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Septet: [Sextet, Septet, Quintet, Quartet, Triplet, Pair, Unit]

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
            // Create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = new Sextet<String, String, String, String, String, String>(
                    "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);

            // Create Septet from Sextet
            Septet<String, String, String, String, String, String, String>
                septet = sextet.addAt2("Septet");

            // Print the Septet
            System.out.println("Septet: " + septet);
        }
    }
    ```

    **输出:**

    ```java
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Septet: [Sextet, Quintet, Septet, Quartet, Triplet, Pair, Unit]

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
            // Create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = new Sextet<String, String, String, String, String, String>(
                    "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);

            // Create Septet from Sextet
            Septet<String, String, String, String, String, String, String>
                septet = sextet.addAt3("Septet");

            // Print the Septet
            System.out.println("Septet: " + septet);
        }
    }
    ```

    **输出:**

    ```java
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Septet: [Sextet, Quintet, Quartet, Septet, Triplet, Pair, Unit]

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

            // Create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = new Sextet<String, String, String, String, String, String>(
                    "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);

            // Create Septet from Sextet
            Septet<String, String, String, String, String, String, String>
                septet = sextet.addAt4("Septet");

            // Print the Septet
            System.out.println("Septet: " + septet);
        }
    }
    ```

    **输出:**

    ```java
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Septet: [Sextet, Quintet, Quartet, Triplet, Septet, Pair, Unit]

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
            // Create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = new Sextet<String, String, String, String, String, String>(
                    "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);

            // Create Septet from Sextet
            Septet<String, String, String, String, String, String, String>
                septet = sextet.addAt5("Septet");

            // Print the Septet
            System.out.println("Septet: " + septet);
        }
    }
    ```

    **输出:**

    ```java
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Septet: [Sextet, Quintet, Quartet, Triplet, Pair, Septet, Unit]

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
            // Create Sextet
            Sextet<String, String, String, String, String, String>
                sextet = new Sextet<String, String, String, String, String, String>(
                    "Sextet", "Quintet", "Quartet", "Triplet", "Pair", "Unit");

            // Print the Sextet
            System.out.println("Sextet: " + sextet);

            // Create Septet from Sextet
            Septet<String, String, String, String, String, String, String>
                septet = sextet.addAt6("Septet");

            // Print the Septet
            System.out.println("Septet: " + septet);
        }
    }
    ```

    **输出:**

    ```java
    Sextet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit]
    Septet: [Sextet, Quintet, Quartet, Triplet, Pair, Unit, Septet]

    ```