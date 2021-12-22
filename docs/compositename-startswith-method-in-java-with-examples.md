# Java 中的 CompositeName startsWith()方法，示例

> 原文:[https://www . geesforgeks . org/composite name-starts with-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-startswith-method-in-java-with-examples/)

**javax.naming.CompositeName 类**的**start with()**方法用于检查作为参数传递的复合名称是否是该复合名称的前缀。如果此复合名称对象以“X”结尾，则复合名称“X”是此复合名称的前缀。如果 X 为空或者不是复合名称对象，则返回 false。

**语法:**

```java
public boolean startsWith(Name n)

```

**参数:**该方法接受名称对象 **n** ，这可能是要检查的空组合名称。

**返回值:**如果 n 是一个复合名，并且是这个复合名的前缀，这个方法返回 true，否则返回 false。

以下程序说明了 CompositeName.startsWith()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompositeName.startsWith()

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName("1:2:4:6");
        CompositeName CompositeName2
            = new CompositeName("2:4:6");

        // apply startsWith()
        boolean Flag
            = CompositeName1
                  .startsWith(CompositeName2);

        // print value
        if (Flag)
            System.out.println(
                "CompositeName1 starts with "
                + " CompositeName2");
        else
            System.out.println(
                "CompositeName1 not starts with "
                + " CompositeName2");
    }
}
```

**Output:**

```java
CompositeName1 not starts with  CompositeName2

```

**程序 2:**

```java
// Java program to demonstrate
// CompositeName.startsWith() method

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName(
                "ca/eaaa/daaa/vaaa/a/b/z/y/x/f");
        CompositeName CompositeName2
            = new CompositeName(
                "ca/eaaa/daaa");

        // apply startsWith()
        boolean Flag
            = CompositeName1
                  .startsWith(CompositeName2);

        // print value
        if (Flag)
            System.out.println(
                "CompositeName1 starts with "
                + " CompositeName2");
        else
            System.out.println(
                "CompositeName1 not starts with "
                + " CompositeName2");
    }
}
```

**Output:**

```java
CompositeName1 starts with  CompositeName2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # starts with(javax . naming . name)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#startsWith(javax.naming.Name))