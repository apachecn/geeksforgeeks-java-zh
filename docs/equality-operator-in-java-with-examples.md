# Java 中的等式(==)运算符，示例

> 原文:[https://www . geesforgeks . org/equality-operator-in-Java-with-examples/](https://www.geeksforgeeks.org/equality-operator-in-java-with-examples/)

**==运算符**是 Java 中 **[关系运算符的一种，用于检查等式关系。它在比较后返回一个**布尔结果**，广泛用于](https://www.geeksforgeeks.org/operators-in-java/)[循环语句](https://www.geeksforgeeks.org/loops-in-java/)以及[条件 if-else 语句](https://www.geeksforgeeks.org/decision-making-javaif-else-switch-break-continue-jump/)。**

**语法:**

```
LHS value == RHS value

```

但是，在比较这些值时，通常会出现三种情况:

1.  **案例 1:当 LHS 和 RHS 值都是原始值时**
    这是案例中最简单的。由于原始数据存储在[堆栈存储器](https://www.geeksforgeeks.org/java-memory-management/)中，在这种情况下，从[堆栈存储器](https://www.geeksforgeeks.org/java-memory-management/)中获取双方的实际值并进行比较。如果两者相等，则返回 true，否则返回 false。

**语法:**

```
Actual value == Actual value

```

**示例:**

```
// Java program for using == operator

import java.io.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring primitive values
        int a = 4;
        int b = 4;
        int c = 5;

        // Comparing a and b using == operator
        System.out.println("Are " + a
                           + " and " + b
                           + " equal? "
                           + (a == b));

        // Comparing b and c using == operator
        System.out.println("Are " + b
                           + " and " + c
                           + " equal? "
                           + (b == c));
    }
}
```

**Output:**

```
Are 4 and 4 equal? true
Are 4 and 5 equal? false

```

*   **Case 2: When one of LHS and RHS value is a primitive and the other is reference**
    In this scenario, for the primitive side, the actual value is taken for comparison from the [stack memory](https://www.geeksforgeeks.org/java-memory-management/). But for the reference side, when an array is declared and initialized, the data is stored in the [heap memory](https://www.geeksforgeeks.org/java-memory-management/) and the reference pointer in the [stack memory](https://www.geeksforgeeks.org/java-memory-management/). So all that is in the [stack memory](https://www.geeksforgeeks.org/java-memory-management/) is the memory address.

    **语法:**

    ```
    Actual value == Address value
        OR
    Address value == Actual value

    ```

    因此，当比较基元值和引用值时，程序不会编译并抛出一个错误:

    **Java 代码编译错误:-**

    ```
    prog.java:20: error: incomparable types: int and int[]
                               + (a == b));
                                    ^
    1 error

    ```

    这是因为原语端的值很容易从[堆栈内存](https://www.geeksforgeeks.org/java-memory-management/)中获取，但对于引用端，该值无法获取，因为该值位于[堆内存](https://www.geeksforgeeks.org/java-memory-management/)中。因此出现了错误。

    **示例:**

    ```
    // Java program for using == operator

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Declaring primitive value
            int a = 4;

            // Declaring reference value
            int[] b = { 1, 2, 3, 4 };

            // Comparing a and b using == operator
            System.out.println("Are " + a
                               + " and " + b
                               + " equal? "
                               + (a == b));
        }
    }
    ```

    *   **Case 3: When both of the LHS and RHS value are reference**
    In this scenario, for both the sides, when an array is declared and initialized, the data is stored in the [heap memory](https://www.geeksforgeeks.org/java-memory-management/) and the reference pointer in the [stack memory](https://www.geeksforgeeks.org/java-memory-management/). So both the variables, their address is checked. If both the variables point to the same memory address, then this operator returns true. Else it returns false.

    **语法:**

    ```
    Address value == Address value

    ```

    **示例:**

    ```
    // Java program for using == operator

    import java.io.*;

    public class GFG {
        public static void main(String[] args)
        {

            // Declaring reference value
            int[] a = { 1, 2, 3, 4 };
            int[] b = { 1, 2, 3, 4 };
            int[] c = b;

            // Comparing a and b using == operator
            // Though they both have the same value
            // the output will be false because
            // they both have a different address in the memory
            System.out.println("Are " + a
                               + " and " + b
                               + " equal? "
                               + (a == b));

            // Comparing b and c using == operator
            // Though they both have the same value
            // the output will be true because
            // they both have same address in the memory
            System.out.println("Are " + b
                               + " and " + c
                               + " equal? "
                               + (b == c));
        }
    }
    ```

    **Output:**

    ```
    Are [I@232204a1 and [I@4aa298b7 equal? false
    Are [I@4aa298b7 and [I@4aa298b7 equal? true

    ```