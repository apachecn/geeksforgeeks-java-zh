# LinkedHashSet 包含 Java 中的()方法，示例

> 原文:[https://www . geeksforgeeks . org/link edhashset-contains-method-in-Java-with-examples/](https://www.geeksforgeeks.org/linkedhashset-contains-method-in-java-with-examples/)

在 Java 中，LinkedHashSet 类包含称为 *contains()* 的方法，如果该集合包含指定的元素，则该方法返回 true，否则返回 false。

**语法:**

```
public boolean contains(Object o)
```

**参数:**元素 **o** 作为参数，其在该集合中的存在性将被测试。

**返回类型:**一个布尔值， **true** 如果这个集合包含指定的元素。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate contains() Method
// of LinkedHashSet class
// For String value

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating an empty LinkedHashSet
            // Declaring object of string type
            LinkedHashSet<String> linkset
                = new LinkedHashSet<String>();

            // Populating above HashSet
            linkset.add("A");
            linkset.add("B");
            linkset.add("C");

            // Printing all elements of above LinkedHashSet
            System.out.println("LinkedHashSet: " + linkset);

            // Checking the existence of element
            // using contains() method
            boolean exist = linkset.contains("C");

            // Printing boolean value if present or not
            System.out.println("Is the element"
                               + " 'C' present: " + exist);
        }

        // Catch block to check for exceptions
        catch (NullPointerException e) {

            // Display message if exception occurs
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
LinkedHashSet: [A, B, C]
Is the element 'C' present: true
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to Illustrate contains() Method
// of LinkedHashSet class
// For Integer value

// Importing required classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] argv) throws Exception
    {

        // Try block to check for exceptions
        try {

            // Creating an empty LinkedHashSet
            // Declaring object of integer type
            LinkedHashSet<Integer> linkset
                = new LinkedHashSet<Integer>();

            // Populating above HashSet
            linkset.add(10);
            linkset.add(20);
            linkset.add(30);

            // Printing all elements of above LinkedHashSet
            System.out.println("LinkedHashSet: " + linkset);

            // Checking the existence of element
            // using contains() method
            boolean exist = linkset.contains(25);

            // Printing boolean value if present or not
            System.out.println("Is the element"
                               + " '25' present: " + exist);
        }

        // Catch block to check for exceptions
        catch (NullPointerException e) {

            // Display message if exception occurs
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
LinkedHashSet: [10, 20, 30]
Is the element '25' present: false
```