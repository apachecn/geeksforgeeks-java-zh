# 如何在 Java 中将数组转换为字符串？

> 原文:[https://www . geesforgeks . org/如何在 java 中将数组转换为字符串/](https://www.geeksforgeeks.org/how-to-convert-an-array-to-string-in-java/)

以下是在 Java 中将数组转换为字符串的各种方法:

1.  **[Arrays.toString()方法](https://www.geeksforgeeks.org/arrays-tostring-in-java-with-examples/) :** Arrays.toString()方法用于返回指定数组内容的字符串表示形式。字符串表示形式由包含在方括号(“[]”)中的数组元素列表组成。相邻的元素由字符“，”(逗号后跟空格)分隔。如果数组为空，则返回“null”。

    ```java
    // Java program to demonstrate
    // working of Arrays.toString()

    import java.io.*;
    import java.util.*;

    class GFG {
        public static void main(String[] args)
        {

            // Let us create different types of arrays and
            // print their contents using Arrays.toString()
            boolean[] boolArr
                = new boolean[] { true, true, false, true };
            char[] charArr
                = new char[] { 'g', 'e', 'e', 'k', 's' };
            double[] dblArr
                = new double[] { 1, 2, 3, 4 };
            int[] intArr
                = new int[] { 1, 2, 3, 4 };
            Object[] objArr
                = new Object[] { 1, 2, 3, 4 };

            System.out.println(
                "Boolean Array: "
                + Arrays.toString(boolArr));
            System.out.println(
                "Character Array: "
                + Arrays.toString(charArr));
            System.out.println(
                "Double Array: "
                + Arrays.toString(dblArr));
            System.out.println(
                "Integer Array: "
                + Arrays.toString(intArr));
            System.out.println(
                "Object Array: "
                + Arrays.toString(objArr));
        }
    }
    ```

    **输出:**

    ```java
    Boolean Array: [true, true, false, true]
    Character Array: [g, e, e, k, s]
    Double Array: [1.0, 2.0, 3.0, 4.0]
    Integer Array: [1, 2, 3, 4]
    Object Array: [1, 2, 3, 4]

    ```

2.  **[StringBuilder append(char[])](https://www.geeksforgeeks.org/stringbuilder-append-method-in-java-with-examples/):**Java . lang . StringBuilder . append(char[])是将 char 数组参数的字符串表示形式附加到这个 StringBuilder 序列的内置方法。

    ```java
    // Java program to illustrate the
    // StringBuilder.append(char[]) method

    import java.lang.*;

    public class Geeks {

        public static void main(String[] args)
        {

            StringBuilder sbf
                = new StringBuilder("We are geeks ");
            System.out.println(sbf);

            // Char array
            char[] astr
                = new char[] { 'G', 'E', 'E', 'k', 'S' };

            // Appends string representation of char
            // array to this String Builder
            sbf.append(astr);
            System.out.println("Result after"
                               + " appending = "
                               + sbf);

            sbf = new StringBuilder("We are -");
            System.out.println(sbf);

            // Char array
            astr = new char[] { 'a', 'b', 'c', 'd' };

            /* Appends string representation of char 
                    array to this StringBuilder */
            sbf.append(astr);
            System.out.println("Result after appending = " + sbf);
        }
    }
    ```

    **输出:**

    ```java
    We are geeks 
    Result after appending = We are geeks GEEkS
    We are -
    Result after appending = We are -abcd

    ```