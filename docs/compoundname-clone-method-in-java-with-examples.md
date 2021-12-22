# Java 中的 CompoundName 克隆()方法，示例

> 原文:[https://www . geesforgeks . org/compound name-clone-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-clone-method-in-java-with-examples/)

一个 **javax.naming.CompoundName 类**的 **clone()** 方法用于返回这个复合名称对象的副本。如果您对此原始复合名称的组件进行任何更改，都不会影响复合名称对象的新副本，反之亦然。克隆和这个复合名称使用相同的语法。

**语法:**

```java
public Object clone()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该复合名称的非空副本。

下面的程序说明了 CompoundName.clone()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompoundName.clone()

import java.util.Enumeration;
import java.util.Properties;

import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "|");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create CompoundName object
        CompoundName CompoundName
            = new CompoundName(
                "x|y", props);

        // create clone object
        CompoundName cloneCompound
            = (CompoundName)CompoundName
                  .clone();

        // print cloned CompoundName
        System.out.println(
            "Clone CompoundName: "
            + cloneCompound);

        // print members
        System.out.println("Members:");
        Enumeration<String> enumeration
            = cloneCompound.getAll();
        while (enumeration.hasMoreElements())
            System.out.print(
                enumeration.nextElement() + " ");
    }
}
```

**Output:**

```java
Clone CompoundName: x|y
Members:
x y

```

**程序 2:**

```java
// Java program to demonstrate
// CompoundName.clone() method

import java.util.Enumeration;
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

        // create CompoundName object
        CompoundName CompoundName
            = new CompoundName(
                "x:y:z:a:m:a:q:e",
                props);

        // create clone object
        CompoundName cloneCompound
            = (CompoundName)CompoundName
                  .clone();

        // print cloned CompoundName
        System.out.println("Clone CompoundName: "
                           + cloneCompound);

        // print members
        System.out.println("Members:");
        Enumeration<String> enumeration
            = cloneCompound.getAll();
        int i = 1;
        while (enumeration.hasMoreElements()) {
            System.out.println(i + ":"
                               + enumeration.nextElement());
            i++;
        }
    }
}
```

**Output:**

```java
Clone CompoundName: x:y:z:a:m:a:q:e
Members:
1:x
2:y
3:z
4:a
5:m
6:a
7:q
8:e

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # clone()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#clone())