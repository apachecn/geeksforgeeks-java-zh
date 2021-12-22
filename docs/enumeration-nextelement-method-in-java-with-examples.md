# 用示例枚举 Java 中的 nextElement()方法

> 原文:[https://www . geesforgeks . org/enumeration-next element-method-in-Java-with-examples/](https://www.geeksforgeeks.org/enumeration-nextelement-method-in-java-with-examples/)

实现**枚举接口**的对象生成一系列元素，一次一个。**枚举**的 **nextElement()** 方法，用于返回该枚举的下一个元素，前提是该枚举对象至少还有一个元素要提供。此方法用于从枚举中获取元素。

**语法:**

```java
E nextElement()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回真这个枚举的下一个元素。

**异常:**如果没有更多元素存在，这个方法抛出 NoSuchElementException。

下面的程序说明了 nextElement()方法:
**程序 1:**

```java
// Java program to demonstrate
// Enumeration.nextElement() method

import java.util.*;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        // create a Enumeration and vector object
        Enumeration<Integer> company;
        Vector<Integer> employees = new Vector<Integer>();

        // add values to employees
        employees.add(1001);
        employees.add(2001);
        employees.add(3001);
        employees.add(4001);
        company = employees.elements();

        while (company.hasMoreElements()) {
            // get elements using nextElement()
            System.out.println("Emp ID = "
                               + company.nextElement());
        }
    }
}
```

**Output:**

```java
Emp ID = 1001
Emp ID = 2001
Emp ID = 3001
Emp ID = 4001

```

**程序 2:**

```java
// Java program to demonstrate
// Enumeration.nextElement() method

import java.util.*;

public class GFG {

    @SuppressWarnings({ "unchecked", "rawtypes" })
    public static void main(String[] args)
    {

        // create a Enumeration and vector object
        Enumeration<String> Users;
        Vector<String> user = new Vector<String>();

        // add Users
        user.add("Aman Singh");
        user.add("Raunak Singh");
        user.add("Siddhant Gupta");
        Users = user.elements();

        while (Users.hasMoreElements()) {
            // get elements using nextElement()
            System.out.println(Users.nextElement());
        }
    }
}
```

**Output:**

```java
Aman Singh
Raunak Singh
Siddhant Gupta

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/util/enumeration . html # nextElement()](https://docs.oracle.com/javase/10/docs/api/java/util/Enumeration.html#nextElement())