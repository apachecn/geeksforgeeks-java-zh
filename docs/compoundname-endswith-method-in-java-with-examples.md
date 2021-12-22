# Java 中的 CompoundName endsWith()方法，带示例

> 原文:[https://www . geesforgeks . org/compound name-end swith-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-endswith-method-in-java-with-examples/)

**javax.naming.CompoundName 类**的 **endsWith()** 方法用于检查作为参数传递的复合名称是否是该复合名称的后缀。如果复合名称对象以“X”结尾，则复合名称“X”是该复合名称的后缀。如果 X 为空或者不是复合名称对象，则返回 false。

**语法:**

```java
public boolean endsWith(Name n)

```

**参数:**此方法接受 n，n 是要检查的可能为空的复合名称。

**返回值:**如果 n 是 CompoundName，并且是该复合名称的后缀，则该方法返回 true，否则返回 false。

下面的程序说明了 CompoundName.endsWith()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompoundName.endsWith()

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
                "a:b:z:y:x", props);
        CompoundName CompoundName2
            = new CompoundName(
                "z:y:x", props);

        // apply endsWith()
        boolean endWithFlag
            = CompoundName1
                  .endsWith(CompoundName2);

        // print value
        if (endWithFlag)
            System.out.println(
                "CompoundName1 ends with "
                + " CompoundName2");
        else
            System.out.println(
                "CompoundName1 not ends with "
                + " CompoundName2");
    }
}
```

**Output:**

```java
CompoundName1 ends with  CompoundName2

```

**程序 2:**

```java
// Java program to demonstrate
// CompoundName.endsWith() method

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
                "z/y/x",
                props);

        // apply endsWith()
        boolean endWithFlag
            = CompoundName1
                  .endsWith(CompoundName2);

        // print value
        if (endWithFlag)
            System.out.println(
                "CompoundName1 ends with "
                + " CompoundName2");
        else
            System.out.println(
                "CompoundName1 not ends with "
                + " CompoundName2");
    }
}
```

**Output:**

```java
CompoundName1 not ends with  CompoundName2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # endsWith(javax . naming . name)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#endsWith(javax.naming.Name))