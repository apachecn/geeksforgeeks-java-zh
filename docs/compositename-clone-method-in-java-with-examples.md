# Java 中的 CompositeName clone()方法，示例

> 原文:[https://www . geesforgeks . org/composite name-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-clone-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **clone()** 方法用于返回这个复合名称对象的副本。如果您对此原始复合名称的组件进行任何更改，都不会影响复合名称对象的新副本，反之亦然。

**语法:**

```java
public Object clone()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该复合名称的非空副本。

下面的程序说明了 CompositeName.clone()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompositeName.clone()

import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create Composite name object
        CompositeName compositeName
            = new CompositeName("x/y");

        // create clone object
        CompositeName cloneComposite
            = (CompositeName)compositeName.clone();

        // print CompositeName
        System.out.println("Clone CompositeName: "
                           + cloneComposite);
    }
}
```

**Output:**

```java
Clone CompositeName: x/y

```

**程序 2:**

```java
// Java program to demonstrate
// CompositeName.clone() method

import java.util.Enumeration;

import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create Composite name object
        CompositeName compositeName
            = new CompositeName("x/y/z/a");

        // create clone object
        CompositeName cloneComposite
            = (CompositeName)compositeName.clone();

        // print CompositeName
        System.out.println("Clone CompositeName: "
                           + cloneComposite);
        System.out.print("Members: ");
        Enumeration<String> enumeration
            = cloneComposite.getAll();
        while (enumeration.hasMoreElements())
            System.out.print(enumeration.nextElement()
                             + ", ");
    }
}
```

**Output:**

```java
Clone CompositeName: x/y/z/a
Members: x, y, z, a,

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # clone()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#clone())