# Java 逻辑运算符示例

> 原文:[https://www . geesforgeks . org/Java-logic-operators-with-examples/](https://www.geeksforgeeks.org/java-logical-operators-with-examples/)

**[运算符](https://www.geeksforgeeks.org/operators-in-java/)** 构成了任何编程语言的基本构件。Java 也提供了许多类型的运算符，可以根据需要使用它们来执行各种计算和功能，包括逻辑、算术、关系等。它们根据提供的功能进行分类。以下是几种类型:

1.  算术运算符
2.  一元运算符
3.  赋值运算符
4.  关系运算符
5.  逻辑运算符
6.  三元算子
7.  按位运算符
8.  移位运算符

本文解释了关于逻辑运算符需要知道的所有内容。

**逻辑运算符**

这些运算符用于执行逻辑“与”、“或”和“非”操作，即类似于数字电子技术中的“与”门和“或”门的功能。它们用于组合两个或多个条件/约束，或在特定考虑下补充原始条件的评估。需要记住的一点是，如果第一个条件为假，则不评估第二个条件，即它具有短路效应。广泛用于测试做决定的几个条件。让我们详细看看每个逻辑运算符:

1.  **‘Logical AND’ Operator(&&):** This operator returns true when both the conditions under consideration are satisfied or are true. If even one of the two yields false, the operator results false. For example, cond1 && cond2 returns true when both cond1 and cond2 are true (i.e. non-zero).
    **Syntax:**

    ```java
    condition1 && condition2
    ```

    **示例:**

    ```java
    a = 10, b = 20, c = 20

    condition1: a < b
    condition2: b == c

    if(condition1 && condition2)
    d = a+b+c

    // Since both the conditions are true
    d = 50.
    ```

    ```java
    // Java code to illustrate
    // logical AND operator

    import java.io.*;

    class Logical {
        public static void main(String[] args)
        {
            // initializing variables
            int a = 10, b = 20, c = 20, d = 0;

            // Displaying a, b, c
            System.out.println("Var1 = " + a);
            System.out.println("Var2 = " + b);
            System.out.println("Var3 = " + c);

            // using logical AND to verify
            // two constraints
            if ((a < b) && (b == c)) {
                d = a + b + c;
                System.out.println("The sum is: " + d);
            }
            else
                System.out.println("False conditions");
        }
    }
    ```

    **Output:**

    ```java
    Var1 = 10
    Var2 = 20
    Var3 = 20
    The sum is: 50

    ```

2.  **'Logical OR' Operator(||):** This operator returns true when one of the two conditions under consideration are satisfied or are true. If even one of the two yields true, the operator results true. To make the result false, both the constraints need to return false.
    **Syntax:**

    ```java
    condition1 || condition2
    ```

    **示例:**

    ```java
    a = 10, b = 20, c = 20

    condition1: a < b
    condition2: b > c

    if(condition1 || condition2)
    d = a+b+c

    // Since one of the condition is true
    d = 50.
    ```

    ```java
    // Java code to illustrate
    // logical OR operator

    import java.io.*;

    class Logical {
        public static void main(String[] args)
        {
            // initializing variables
            int a = 10, b = 1, c = 10, d = 30;

            // Displaying a, b, c
            System.out.println("Var1 = " + a);
            System.out.println("Var2 = " + b);
            System.out.println("Var3 = " + c);
            System.out.println("Var4 = " + d);

            // using logical OR to verify
            // two constraints
            if (a > b || c == d)
                System.out.println("One or both"
                                   + " the conditions are true");
            else
                System.out.println("Both the"
                                   + " conditions are false");
        }
    }
    ```

    **Output:**

    ```java
    Var1 = 10
    Var2 = 1
    Var3 = 10
    Var4 = 30
    One or both the conditions are true

    ```

3.  **'Logical NOT' Operator(!):** Unlike the previous two, this is a unary operator and returns true when the condition under consideration is not satisfied or is a false condition. Basically, if the condition is false, the operation returns true and when the condition is true, the operation returns false.

    **语法:**

    ```java
    !(condition)
    ```

    **示例:**

    ```java
    a = 10, b = 20

    !(a<b) // returns false
    !(a>b) // returns true

    ```

    ```java
    // Java code to illustrate
    // logical NOT operator
    import java.io.*;

    class Logical {
        public static void main(String[] args)
        {
            // initializing variables
            int a = 10, b = 1;

            // Displaying a, b, c
            System.out.println("Var1 = " + a);
            System.out.println("Var2 = " + b);

            // Using logical NOT operator
            System.out.println("!(a < b) = " + !(a < b));
            System.out.println("!(a > b) = " + !(a > b));
        }
    }
    ```

    **Output:**

    ```java
    Var1 = 10
    Var2 = 1
    !(a < b) = true
    !(a > b) = false

    ```