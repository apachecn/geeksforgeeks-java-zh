# Java 中的 Collections checkedMap()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-checked map-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-checkedmap-method-in-java-with-examples/)

[Collections 类](https://www.geeksforgeeks.org/collections-class-in-java/)的 ***checkedMap()*** 方法已经存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中，用于返回指定地图的动态类型安全视图。如果指定的映射是可序列化的，则返回的映射是可序列化的。因为 null 被认为是任何引用类型的值，所以只要后备映射允许，返回的映射就允许插入 null 键或值。

**语法:**

```java
public static  Map 
checkedMap(Map m, Class keyType, Class valueType)
```

**参数:**该方法将以下 3 个参数作为参数，如下所示:

*   要返回动态类型安全视图的映射
*   允许 m 持有的钥匙类型
*   允许 m 持有的值的类型

**返回值:**该方法动态返回指定地图的**类型安全视图**。

**异常:**这个方法确实抛出了 [ClassCastException](https://www.geeksforgeeks.org/how-to-fix-java-lang-classcastexception-in-java/)

> **提示:**该方法兼容 java 版及以后版本。

现在让我们看几个例子，以便实现上述方法，并更好地理解如下方法:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Demonstrate checkedMap() method
// of Collections class

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating an empty HashMap by declaring
            // HashMap key-value pairs
            //  of string and string type
            HashMap<String, String> hmap
                = new HashMap<String, String>();

            // Adding custom key-value pairs to above
            // HashMap
            hmap.put("Ram", "Shyam");
            hmap.put("Karan", "Arjun");
            hmap.put("Karn", "Veer");
            hmap.put("duryodhan", "dhrupat");

            // Printing all the key-value pairs of above
            // HashMap
            System.out.println("Map: \n" + hmap);

            // Now creating typesafe view of the specified
            // map using checkedMap() method of Collections
            // class
            Map<String, String> tsmap
                = Collections.checkedMap(hmap, String.class,
                                         String.class);

            // Now printing the typesafe view of specified
            // list
            System.out.println("Typesafe view of Map: "
                               + tsmap);
        }

        // Catch block to handle the exceptions
        catch (IllegalArgumentException e) {

            // Display message when exception occurs
            System.out.println("Exception thrown : \n" + e);
        }
    }
}
```

**Output:** 

```java
Map: 
{Karn=Veer, Karan=Arjun, duryodhan=dhrupat, Ram=Shyam}
Typesafe view of Map: 
{Karn=Veer, Karan=Arjun, duryodhan=dhrupat, Ram=Shyam}
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate checkedMap() method
// of Collections class

// Importing all required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating an empty HashMap by
            // declaring object of string and integer type
            HashMap<String, Integer> hmap
                = new HashMap<String, Integer>();

            // Adding key-value pairs to above HashMap
            // object
            hmap.put("Player-1", 20);
            hmap.put("Player-2", 30);
            hmap.put("Player-3", 40);

            // Printing the elements inside above HashMap
            // object
            System.out.println("Map: \n" + hmap);

            // Now creating typesafe view of the specified
            // map using checkedMap() method
            Map<String, Integer> tsmap
                = Collections.checkedMap(hmap, String.class,
                                         Integer.class);

            // Again printing the typesafe view of specified
            // list
            System.out.println("Typesafe view of Map: \n"
                               + tsmap);
        }

        // Catch block to handle exceptions
        catch (IllegalArgumentException e) {

            // Display message when exception occurs
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
Map: 
{Player-1=20, Player-3=40, Player-2=30}
Typesafe view of Map: 
{Player-1=20, Player-3=40, Player-2=30}
```