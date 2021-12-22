# Java 中的 CompoundName startsWith()方法，示例

> 原文:[https://www . geesforgeks . org/compound name-starts with-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-startswith-method-in-java-with-examples/)

**javax.naming.CompoundName 类**的**start with()**方法用于检查作为参数传递的复合名称是否是该复合名称的前缀。如果复合名称对象以“X”结尾，则复合名称“X”是该复合名称的前缀。如果 X 为空或者不是复合名称对象，则返回 false。

**语法:**

```java
public boolean startsWith(Name n)

```

**参数:**此方法接受 **n** ，这是可能为空的要检查的复合名称。

**返回值:**如果 n 是 CompoundName，并且是该复合名称的前缀，则该方法返回 true，否则返回 false。

以下程序说明了 CompoundName.startsWith()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompoundName.startsWith()

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
                "1:2:4:6", props);
        CompoundName CompoundName2
            = new CompoundName(
                "2:4:6", props);

        // apply startsWith()
        boolean Flag
            = CompoundName1
                  .startsWith(CompoundName2);

        // print value
        if (Flag)
            System.out.println(
                "CompoundName1 starts with "
                + " CompoundName2");
        else
            System.out.println(
                "CompoundName1 not starts with "
                + " CompoundName2");
    }
}
```

**Output:**

```java
CompoundName1 not starts with  CompoundName2

```

**程序 2:**

```java
// Java program to demonstrate
// CompoundName.startsWith() method

import java.util.Properties;
import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "/");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "c/e/d/v/a/b/z/y/x/f",
                props);
        CompoundName CompoundName2
            = new CompoundName(
                "c/e/d",
                props);

        // apply startsWith()
        boolean Flag
            = CompoundName1
                  .startsWith(CompoundName2);

        // print value
        if (Flag)
            System.out.println(
                "CompoundName1 starts with "
                + " CompoundName2");
        else
            System.out.println(
                "CompoundName1 not starts with "
                + " CompoundName2");
    }
}
```

**Output:**

```java
CompoundName1 starts with  CompoundName2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # starts with(javax . naming . name)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#startsWith(javax.naming.Name))