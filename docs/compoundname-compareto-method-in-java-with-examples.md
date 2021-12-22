# Java 中的 CompoundName compareTo()方法与示例

> 原文:[https://www . geesforgeks . org/compound name-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-compareto-method-in-java-with-examples/)

**javax.naming.CompoundName 类**的 **compareTo()** 方法用于将该 CompoundName 与作为参数传递的指定对象进行比较。它返回负整数、零或正整数，因为此 CompoundName 对象小于、等于或大于给定的对象作为参数。如果传递的对象为空或者不是 CompoundName 的实例，则该方法将引发 ClassCastException。

**语法:**

```
public int compareTo(Object obj)

```

**参数:**该方法接受**对象**，该对象是非空对象进行比较。

**返回值:**此方法返回一个负整数、零或正整数，因为此名称小于、等于或大于给定的对象。

**异常:**如果传递的对象不是一个 CompoundName 对象，这个方法抛出 **ClassCastException** 。

下面的程序说明了 CompoundName.compareTo()方法:
**程序 1:**

```
// Java program to demonstrate
// CompoundName.compareTo()

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
            = new CompoundName("x:y:z",
                               props);
        CompoundName CompoundName2
            = new CompoundName("x:y:m",
                               props);

        // apply compareTo()
        int value
            = CompoundName1
                  .compareTo(CompoundName2);

        // print value
        if (value > 0)
            System.out.println(
                "CompoundName1 is "
                + "greater than CompoundName2");
        else if (value < 0)
            System.out.println(
                "CompoundName1 is "
                + "smaller than CompoundName2");
        else
            System.out.println(
                "CompoundName1 is "
                + "equal to CompoundName2");
    }
}
```

**Output:**

```
CompoundName1 is greater than CompoundName2

```

**程序 2:**

```
// Java program to demonstrate
// CompoundName.compareTo() method

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
                "x@y@z@M@n",
                props);
        CompoundName CompoundName2
            = new CompoundName(
                "x@y@z@M@n",
                props);

        // apply compareTo()
        int value
            = CompoundName1
                  .compareTo(CompoundName2);

        // print value
        if (value > 0)
            System.out.println(
                "CompoundName1 is "
                + "greater than CompoundName2");
        else if (value < 0)
            System.out.println(
                "CompoundName1 is "
                + "smaller than CompoundName2");
        else
            System.out.println(
                "CompoundName1 is "
                + "equal to CompoundName2");
    }
}
```

**Output:**

```
CompoundName1 is equal to CompoundName2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # compare to(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#compareTo(java.lang.Object))