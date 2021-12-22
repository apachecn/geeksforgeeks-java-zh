# Java 中的 Collections addAll()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-addall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-addall-method-in-java-with-examples/)

**java.util.Collections** 类的 **addAll()** 方法用于将所有指定的元素添加到指定的集合中。要添加的元素可以单独指定，也可以作为数组指定。这种便捷方法的行为与 c . addall(arrays . aslist(elements))相同，但在大多数实现下，这种方法的运行速度可能会明显加快。

**语法:**

```java
public static  boolean 
    addAll(Collection c, T... elements)
```

**参数:**该方法采用以下参数作为参数

*   **c-** 要插入元素的集合
*   **元素-** 要插入 c 的元素

**返回值:**如果集合因调用而改变，则该方法返回 true。

**异常:**如果元素包含一个或多个空值，并且 c 不允许空元素，或者如果 c 或元素为空，则该方法抛出**空指针异常**

以下是说明 *addAll()* 方法的示例

**例 1:**

```java
// Java program to demonstrate
// addAll() method

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of List<String>
            List<String> arrlist = new ArrayList<String>();

            // Adding element to arrlist
            arrlist.add("A");
            arrlist.add("B");
            arrlist.add("C");
            arrlist.add("Tajmahal");

            // printing the arrlist before operation
            System.out.println("arrlist before operation : " + arrlist);

            // add the specified element to specified Collections
            // using addAll() method
            boolean b = Collections.addAll(arrlist, "1", "2", "3");

            // printing the arrlist after operation
            System.out.println("result : " + b);

            // printing the arrlist after operation
            System.out.println("arrlist after operation : " + arrlist);
        }

        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
arrlist before operation : [A, B, C, Tajmahal]
result : true
arrlist after operation : [A, B, C, Tajmahal, 1, 2, 3]

```

**输出:**

```java
arrlist before operation : [A, B, C, Tajmahal]
result : true
arrlist after operation : [A, B, C, Tajmahal, 1, 2, 3]
```

**示例 2:** 适用于*空指针异常*

```java
// Java program to demonstrate
// addAll() method

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of List<String>
            List<String> arrlist = new ArrayList<String>();

            // Adding element to arrlist
            arrlist.add("A");
            arrlist.add("B");
            arrlist.add("C");
            arrlist.add("Tajmahal");

            // printing the arrlist before operation
            System.out.println("arrlist before operation : " + arrlist);

            // add the specified element to specified Collections
            // using addAll() method
            System.out.println("\nTrying to add the null value with arrlist");
            boolean b = Collections.addAll(null, arrlist);

            // printing the arrlist after operation
            System.out.println("result : " + b);

            // printing the arrlist after operation
            System.out.println("arrlist after operation : " + arrlist);
        }

        catch (NullPointerException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (IllegalArgumentException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
arrlist before operation : [A, B, C, Tajmahal]

Trying to add the null value with arrlist
Exception thrown : java.lang.NullPointerException

```