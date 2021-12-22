# 用示例替换 Java 中的 Collections replaceAll()方法

> 原文:[https://www . geesforgeks . org/collections-replace all-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-replaceall-method-in-java-with-examples/)

**java.util.Collections** 类的 **replaceAll()** 方法用于将列表中一个指定值的所有出现替换为另一个。更正式地说，用 newVal 替换列表中的每个元素 e，这样

```java
oldVal == null ? e==null : oldVal.equals(e) 
```

> **注意:**此方法对列表大小没有影响。

**参数:**该方法将以下参数作为参数

*   **列表:**要进行替换的列表。
*   **旧值:**要替换的旧值。
*   **新值:**替换旧值的新值。

**返回值:**如果列表包含如下所示的一个或多个元素 e，则该方法返回 **true** 否则返回 false

```java
oldVal== null ? e==null : oldVal.equals(e)
```

**语法:**

```java
public static  boolean replaceAll(List list, T oldVal, T newVal)
```

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// replaceAll() method for String value

// Importing utility classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating a vector object of string type
            List<String> vector = new Vector<String>();

            // Populating the above Vector object
            // Custom input elements
            vector.add("A");
            vector.add("B");
            vector.add("A");
            vector.add("C");

            // Printing the vector
            System.out.println("Initial Vector :" + vector);

            // Replacing value
            // using replaceAll() method
            Collections.replaceAll(vector, "A", "TAJMAHAL");

            // Printitng elements of Vector object after
            // replacing
            System.out.println("Vector after replace :"
                               + vector);
        }

        // Catch block to handle the exceptions
        catch (IllegalArgumentException e) {

            // Display message when exception occurs
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output**

```java
Initial Vector :[A, B, A, C]
Vector after replace :[TAJMAHAL, B, TAJMAHAL, C]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// replaceAll() method for Integer value

// importing utility classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating object of List<String>
            List<Integer> vector = new Vector<Integer>();

            // Populate the vector
            vector.add(20);
            vector.add(30);
            vector.add(20);
            vector.add(30);

            // Printing the vector before replacing
            // elemements
            System.out.println("Initial values are :"
                               + vector);

            // Replacing value
            // using replaceAll() method
            Collections.replaceAll(vector, 20, 400);

            // Printing the vector after replacing elements
            System.out.println("Value after replace :"
                               + vector);
        }

        // Catch block to handle IllegalArgumentException
        catch (IllegalArgumentException e) {

            // Display the exceptions on the console
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Initial values are :[20, 30, 20, 30]
Value after replace :[400, 30, 400, 30]
```