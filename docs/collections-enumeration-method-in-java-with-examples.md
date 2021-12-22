# Java 中的集合枚举()方法，带示例

> 原文:[https://www . geesforgeks . org/collections-enumeration-method-in-Java-with-examples/](https://www.geeksforgeeks.org/collections-enumeration-method-in-java-with-examples/)

**java.util.Collections** 类的**枚举()**方法用于返回指定集合的枚举。这提供了与需要枚举作为输入的遗留 API 的互操作性。
**语法:**

```
public static  Enumeration enumeration(Collection c)
```

**参数:**该方法将集合 **c** 作为要返回枚举的参数。
**返回值:**该方法返回指定集合的**枚举**。
以下是举例说明*枚举()*方法
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// enumeration() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of List<String>
            List<String> arrlist = new ArrayList<String>();

            // Adding element to srclst
            arrlist.add("Ram");
            arrlist.add("Gopal");
            arrlist.add("Verma");

            // Print the list
            System.out.println("List: " + arrlist);

            // creating object of type Enumeration<String>
            Enumeration<String> e = Collections.enumeration(arrlist);

            // Print the Enumeration
            System.out.println("\nEnumeration over list: ");

            // print the enumeration
            while (e.hasMoreElements())
                System.out.println("Value is: " + e.nextElement());
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
List: [Ram, Gopal, Verma]

Enumeration over list: 
Value is: Ram
Value is: Gopal
Value is: Verma
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// enumeration() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv) throws Exception
    {
        try {

            // creating object of List<Integer>
            List<Integer> arrlist = new ArrayList<Integer>();

            // Adding element to srclst
            arrlist.add(20);
            arrlist.add(30);
            arrlist.add(40);

            // Print the list
            System.out.println("List: " + arrlist);

            // creating object of type Enumeration<Integer>
            Enumeration<Integer> e = Collections.enumeration(arrlist);

            // Print the Enumeration
            System.out.println("\nEnumeration over list: ");

            // print the enumeration
            while (e.hasMoreElements())
                System.out.println("Value is: " + e.nextElement());
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception thrown : " + e);
        }

        catch (NoSuchElementException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
List: [20, 30, 40]

Enumeration over list: 
Value is: 20
Value is: 30
Value is: 40
```