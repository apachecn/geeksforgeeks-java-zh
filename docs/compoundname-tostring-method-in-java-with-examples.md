# Java 中的 CompoundName toString()方法，带示例

> 原文:[https://www . geesforgeks . org/compound name-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-tostring-method-in-java-with-examples/)

一个 **javax.naming.CompoundName 类**的 **toString()** 方法用于使用通过属性传递的复合名称的语法来创建这个复合名称对象的字符串表示。如果组件是空的，则用空字符串表示。创建的非空复合名称对象的字符串表示形式具有相同的语法属性，并且所有组件都由字符串表示形式中的该语法分隔。

**语法:**

```
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该复合名称的非空字符串表示。

下面的程序说明了 CompoundName.toString()方法:
**程序 1:**

```
// Java program to demonstrate
// CompoundName.toString()

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

        // apply toString()
        String toString
            = CompoundName1.toString();

        // print value
        System.out.println("toString: "
                           + toString);
    }
}
```

**Output:**

```
toString: 1@2@3@4@5@6@7

```

**程序 2:**

```
// Java program to demonstrate
// CompoundName.toString() method

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

        // apply toString()
        String toString
            = CompoundName1.toString();

        // print value
        System.out.println("CompoundName:"
                           + toString);
    }
}
```

**Output:**

```
CompoundName:c/e/d/v/a/b/z/y/x/f

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # toString()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#toString())