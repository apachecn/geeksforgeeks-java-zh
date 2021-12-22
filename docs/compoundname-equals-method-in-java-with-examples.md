# Java 中的 CompoundName 等于()方法，示例

> 原文:[https://www . geesforgeks . org/compound name-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-equals-method-in-java-with-examples/)

**javax.naming.CompoundName 类**的 **equals()** 方法用于将此 CompoundName 与作为参数传递的指定对象进行比较，并检查两个对象是否相等。如果两个对象相等，那么 equals()方法返回 true，否则返回 false。如果传递的 obj 为 null 或不是复合名称，则该方法返回 false。如果一个对象中的每个组件与另一个对象中的相应组件相等，则两个复合对象相等。

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该方法接受**对象**，该对象是非空对象进行比较。

**返回值:**如果 obj 等于这个复合名称，这个方法返回 true，否则返回 false。

下面的程序说明了 CompoundName.equals()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompoundName.equals()

import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", ":");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "x:y:z", props);
        CompoundName CompoundName2
            = new CompoundName(
                "x:y:m", props);

        // apply equals()
        boolean flag
            = CompoundName1
                  .equals(CompoundName2);

        // print value
        if (flag)
            System.out.println(
                "CompoundName1 is "
                + "equal to CompoundName2");
        else
            System.out.println(
                "CompoundName1 is "
                + "not equal to CompoundName2");
    }
}
```

**Output:**

```java
CompoundName1 is not equal to CompoundName2

```

**程序 2:**

```java
// Java program to demonstrate
// CompoundName.equals() method

import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "@");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "x@y@z@M@n", props);
        CompoundName CompoundName2
            = new CompoundName(
                "x@y@z@M@n", props);

        // apply equals()
        boolean flag
            = CompoundName1.equals(CompoundName2);

        // print value
        if (flag)
            System.out.println(
                "CompoundName1 is "
                + "equal to CompoundName2");
        else
            System.out.println(
                "CompoundName1 is "
                + "not equal to CompoundName2");
    }
}
```

**Output:**

```java
CompoundName1 is equal to CompoundName2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#equals(java.lang.Object))