# Java 中的 CompoundName getSuffix()方法，带示例

> 原文:[https://www . geesforgeks . org/compound name-get suffix-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-getsuffix-method-in-java-with-examples/)

一个 **javax.naming.CompoundName 类**的 **getSuffix()** 方法用于获取一个复合名称对象，该复合名称对象的组件由该复合名称中组件的后缀组成。我们需要从这个复合名称对象开始提取后缀的位置作为参数传递。返回的复合名称对象和此复合名称对象共享相同的语法。如果我们对这个复合名称进行任何更改，都不会影响返回的名称，反之亦然。

**语法:**

```
public Name getSuffix(int posn)

```

**参数:**该方法接受 posn，posn 是从 0 开始的组件索引。必须在[0，size()]范围内。

**返回值:**该方法返回一个复合名称，该名称由[posn，size()]范围内索引处的组件组成。如果 posn 等于 size()，则返回一个空的复合名称。

**异常:**如果 posn 在指定范围之外，此方法将引发 ArrayIndexOutOfBoundsException。

下面的程序说明了 CompoundName.getSuffix()方法:
**程序 1:**

```
// Java program to demonstrate
// CompoundName.getSuffix()

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
                "1@2@3@4@5@6@7",
                props);

        // apply getSuffix()
        CompoundName newCompoundName
            = (CompoundName)
                  CompoundName1.getSuffix(3);

        // print value
        System.out.println(
            "New CompoundName Object: "
            + newCompoundName);
    }
}
```

**Output:**

```
New CompoundName Object: 4@5@6@7

```

**程序 2:**

```
// Java program to demonstrate
// CompoundName.getSuffix() method

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

        // apply getSuffix()
        CompoundName newCompoundName
            = (CompoundName)
                  CompoundName1.getSuffix(8);

        // print value
        System.out.println(
            "New CompoundName Object: "
            + newCompoundName);
    }
}
```

**Output:**

```
New CompoundName Object: x/f

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # getSuffix(int)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#getSuffix(int))