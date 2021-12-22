# Java 中整数和 int 的区别举例

> 原文:[https://www . geesforgeks . org/Java 中整数和整数之间的差异/](https://www.geeksforgeeks.org/difference-between-an-integer-and-int-in-java/)

在 Java 中， **int 是一个原始数据类型，而 Integer 是一个 Wrapper 类**。

*   Int, as a raw data type, has poor flexibility. We can only store binary values of integers in it.
*   Because Integer is a [wrapper class](https://www.geeksforgeeks.org/wrapper-classes-java/) for int data type, it provides us with more flexibility to store, transform and operate int data.
*   Integer is a class, so you can call various built-in methods defined in the class. Variables of integer type store references to integer objects, just like any other reference (object) type.

**例:**

```java
// Valid
int n = 20;
//valid
Integer n = 45;

// Valid
Integer.parseInt("10");
// Not Valid
int.parseInt("10");

```

**重要区别点:**

1.  **Convert to string variable:** We can't assign string values (only integers) to int variables directly or even through conversion. However, we can use the integer (string) constructor to assign strings to objects of integer type. We can even use parseInt (string) to convert string literals Into int values.

    ```java
    // Java program to illustrate 
    // difference between
    // int and Integer 

    public class Main {
        public static void main(String args[])
        {

            Integer a = new Integer("123");
            // Casting not possible
            // int a = (int)"123";
            // Casting not possible
            // int c="123";

            // Casting possible using methods
            // from Integer Wrapper class
            int b = Integer.parseInt("123");
            System.out.print(a + new Float("10.1"));
        }
    }
    ```

    **Output:**

```java
133.1

```