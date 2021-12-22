# Java 中的 CompositeName 等于()方法，示例

> 原文:[https://www . geesforgeks . org/composite name-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-equals-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **equals()** 方法用于将这个 CompositeName 与作为参数传递的指定对象进行比较，并检查两个对象是否相等。如果两个对象相等，那么 equals()方法返回 true，否则返回 false。如果传递的 obj 为 null 或者不是复合名称，则该方法返回 false。如果一个对象中的每个组件与另一个对象中的相应组件相等，则两个复合对象相等。

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该方法接受对象，该对象可能是要比较的空对象。

**返回值:**如果 obj 等于这个复合名称，这个方法返回 true，否则返回 false。

下面的程序说明了 CompositeName.equals()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompositeName.equals()

import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create Composite name object
        CompositeName compositeName1
            = new CompositeName("x/y/a/b");
        CompositeName compositeName2
            = new CompositeName("x/y/a/b");

        // apply equals()
        boolean flag
            = compositeName1.equals(
                compositeName2);

        // print value
        if (flag)
            System.out.println("CompositeName1 is "
                               + "equal to CompositeName2");
        else
            System.out.println("CompositeName1 is "
                               + "not equal to CompositeName2");
    }
}
```

**Output:**

```java
CompositeName1 is equal to CompositeName2

```

**程序 2:**

```java
// Java program to demonstrate
// CompositeName.equals() method

import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create Composite name object
        CompositeName compositeName1
            = new CompositeName("c/d/a/b");
        CompositeName compositeName2
            = new CompositeName("e/d/a/b");

        // apply equals()
        boolean flag
            = compositeName1.equals(
                compositeName2);

        // print value
        if (flag)
            System.out.println("CompositeName1 is "
                               + "equal to CompositeName2");
        else
            System.out.println("CompositeName1 is "
                               + "not equal to CompositeName2");
    }
}
```

**Output:**

```java
CompositeName1 is not equal to CompositeName2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#equals(java.lang.Object))