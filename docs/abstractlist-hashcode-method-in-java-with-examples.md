# Java 中的抽象列表 hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/abstract list-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractlist-hashcode-method-in-java-with-examples/)

**[Java . util . abstract list](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/)**类的 **hashCode()** 方法用于返回该列表的哈希码值。

**语法:**

```java
public int hashCode()
```

**返回值:**该方法返回该列表的**哈希码**值。

下面是举例说明 *hashCode()* 方法的例子。

**例 1:**

```java
// Java program to demonstrate
// hashCode() method
// for Integer value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of AbstractList<Integer>
            AbstractList<Integer>
                arrlist1 = new ArrayList<Integer>();

            // Populating arrlist1
            arrlist1.add(10);
            arrlist1.add(20);
            arrlist1.add(30);
            arrlist1.add(40);
            arrlist1.add(50);

            // print arrlist1
            System.out.println("ArrayListlist : " + arrlist1);

            // getting the value at the index 3
            // using get() method
            int code = arrlist1.hashCode();

            // print the value
            System.out.println("HashCode : " + code);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
ArrayListlist : [10, 20, 30, 40, 50]
HashCode : 38490301

```

**例 2:**

```java
// Java program to demonstrate
// hashCode() method
// for String value

import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
        throws Exception
    {

        try {

            // Creating object of AbstractList<String>
            AbstractList<String>
                arrlist1 = new ArrayList<String>();

            // Populating arrlist1
            arrlist1.add("A");
            arrlist1.add("B");
            arrlist1.add("C");
            arrlist1.add("D");
            arrlist1.add("E");

            // print arrlist1
            System.out.println("ArrayListlist : "
                               + arrlist1);

            // getting the value at the index 3
            // using get() method
            int code = arrlist1.hashCode();

            // print the value
            System.out.println("HashCode : " + code);
        }

        catch (IndexOutOfBoundsException e) {
            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:**

```java
ArrayListlist : [A, B, C, D, E]
HashCode : 90690786

```