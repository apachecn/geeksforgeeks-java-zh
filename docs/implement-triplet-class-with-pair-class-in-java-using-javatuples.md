# 使用 JavaTuples

在 Java 中用 Pair 类实现三元组类

> 原文:[https://www . geeksforgeeks . org/implement-triple-class-with-pair-class-in-Java-using-javatuples/](https://www.geeksforgeeks.org/implement-triplet-class-with-pair-class-in-java-using-javatuples/)

以下是用[配对类](https://www.geeksforgeeks.org/pair-class-in-java-tuples/)实现[三元组类](https://www.geeksforgeeks.org/triplet-class-in-java-tuples/)的方法

1.  **Using direct values**

    ```java
    import java.util.*;
    import org.javatuples.*;

    class GfG {

        public static void main(String[] args)
        {
            // create Pair
            Pair<Integer, String>
                pair = new Pair<Integer, String>(
                    Integer.valueOf(1), "GeeksforGeeks");

            // Print the Pair
            System.out.println("Pair: " + pair);

            // Create Triplet from Pair
            Triplet<String, Integer, String>
                triplet = new Triplet<String, Integer, String>(
                    "Triplet 1", pair.getValue0(), pair.getValue1());

            // Print the Triplet
            System.out.println("Triplet: " + triplet);
        }
    }
    ```

    **输出:**

    ```java
    Pair: [1, GeeksforGeeks]
    Triplet: [Triplet 1, 1, GeeksforGeeks]
    ```

2.  **Using Pair.add() method**

    ```java
    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // create Pair
            Pair<Integer, String>
                pair = new Pair<Integer, String>(
                    Integer.valueOf(1), "GeeksforGeeks");

            // Print the Pair
            System.out.println("Pair: " + pair);

            // Using add() to create Triplet
            Triplet<Integer, String, String>
                triplet = pair.add("Triplet 1");

            // Print the Triplet
            System.out.println("Triplet: " + triplet);
        }
    }
    ```

    **输出:**

    ```java
    Pair: [1, GeeksforGeeks]
    Triplet: [1, GeeksforGeeks, Triplet 1]
    ```

3.  **Using Pair.addAtX() method**

    **程序 1:** 使用 addAt0()在位置 0 添加

    ```java
    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // create Pair
            Pair<Integer, String>
                pair = new Pair<Integer, String>(
                    Integer.valueOf(1), "GeeksforGeeks");

            // Print the Pair
            System.out.println("Pair: " + pair);

            // Using add() to create Triplet
            Triplet<String, Integer, String>
                triplet = pair.addAt0("Triplet 1");

            // Print the Triplet
            System.out.println("Triplet: " + triplet);
        }
    }
    ```

    **输出:**

    ```java
    Pair: [1, GeeksforGeeks]
    Triplet: [Triplet 1, 1, GeeksforGeeks]
    ```

    **程序 2:** 使用 addAt1()在位置 1 添加

    ```java
    import java.util.*;
    import org.javatuples.*;

    class GfG {
        public static void main(String[] args)
        {
            // create Pair
            Pair<Integer, String>
                pair = new Pair<Integer, String>(
                    Integer.valueOf(1), "GeeksforGeeks");

            // Print the Pair
            System.out.println("Pair: " + pair);

            // Using add() to create Triplet
            Triplet<Integer, String, String>
                triplet = pair.addAt1("Triplet 1");

            // Print the Triplet
            System.out.println("Triplet: " + triplet);
        }
    }
    ```

    **输出:**

    ```java
    Pair: [1, GeeksforGeeks]
    Triplet: [1, Triplet 1, GeeksforGeeks]
    ```

    **程序 2:** 使用 addAt2()在位置 2 添加

    ```java
    // Below is a Java program to demonstrate
    // use of addAt2() method with
    // direct value

    import java.util.*;
    import org.javatuples.*

        class GfG {
        public static void main(String[] args)
        {
            // create Pair
            Pair<Integer, String>
                pair = new Pair<Integer, String>(
                    Integer.valueOf(1), "GeeksforGeeks");

            // Print the Pair
            System.out.println("Pair: " + pair);

            // Using add() to create Triplet
            Triplet<Integer, String, String>
                triplet = pair.addAt2("Triplet 1");

            // Print the Triplet
            System.out.println("Triplet: " + triplet);
        }
    }
    ```

    **输出:**

    ```java
    Pair: [1, GeeksforGeeks]
    Triplet: [1, GeeksforGeeks, Triplet 1]
    ```