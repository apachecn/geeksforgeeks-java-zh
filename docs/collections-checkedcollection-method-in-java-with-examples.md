# Java 中的 Collections checkedCollection()方法，带示例

> 原文:[https://www . geeksforgeeks . org/collections-checked collection-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-checkedcollection-method-in-java-with-examples/)

[java.util.Collections 类](https://www.geeksforgeeks.org/collections-class-in-java/)的 **checkedCollection()** 方法用于返回指定集合的动态类型安全视图。返回的集合不会将 hashCode 和 equals 操作传递给后备集合，而是依赖于 Object 的 equals 和 hashCode 方法。在后备集合是集合或列表的情况下，这对于保留这些操作的契约是必要的。如果指定的集合可序列化，则返回的集合将是可序列化的。

因为 null 被认为是任何引用类型的值，所以每当后备集合插入 null 元素时，返回的集合都允许插入 null 元素。

**语法:**

```java
public static  Collection 
checkedCollection(Collection c, Class type)
```

**参数:**该方法取两个参数

*   要为其返回动态类型安全视图的集合
*   允许 c 持有的元素类型

**返回类型:**该方法动态返回指定集合的**类型安全视图**

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// checkedCollection() method
// for String value

// Importing utility classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating an empty ArrayList by
            // creating object of List of string type
            List<String> arlst = new ArrayList<String>();

            // Adding element to arrlist
            // using add() method

            // Custom input elements
            arlst.add("CSS");
            arlst.add("PHP");
            arlst.add("HTML");
            arlst.add("TajMahal");

            // Printing the ArrayList
            System.out.println("List: " + arlst);

            // Now create typesafe view of the collection bu
            // creating object of Collection class of string
            // type
            Collection<String> tslst
                = Collections.checkedCollection(
                    arlst, String.class);

            // Printing the updated ArrayList
            // after applying checkedCollection() method
            System.out.println("Typesafe view of List: "
                               + tslst);
        }

        // Catch block to handle the exceptions
        catch (IllegalArgumentException e) {

            // Print message to be displayed on console
            // when exception occurs
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
List: [CSS, PHP, HTML, TajMahal]
Typesafe view of List: [CSS, PHP, HTML, TajMahal]
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate checkedCollection() method
// of Collection class for an Integer value

// Importing classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exception
        try {

            // Creating an empty ArrayList of integer type
            // by declaring object of List
            List<Integer> arlst = new ArrayList<Integer>();

            // Adding element to ArrayList
            // using add() method
            arlst.add(20);
            arlst.add(30);
            arlst.add(40);
            arlst.add(50);

            // Printing the above ArrayList
            System.out.println("List: " + arlst);

            // now creating typesafe view of the collection
            // using checkedCollection() method
            Collection<Integer> tslst
                = Collections.checkedCollection(
                    arlst, Integer.class);

            // Printing the updated ArrayList
            // after above operation
            System.out.println("Typesafe view of List: "
                               + tslst);
        }

        // Catch block to handle exceptions
        catch (IllegalArgumentException e) {

            // Display message if exception occurs
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```java
List: [20, 30, 40, 50]
Typesafe view of List: [20, 30, 40, 50]
```