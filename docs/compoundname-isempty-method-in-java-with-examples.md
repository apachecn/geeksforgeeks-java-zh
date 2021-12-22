# Java 中的 CompoundName isEmpty()方法，带示例

> 原文:[https://www . geesforgeks . org/compound name-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-isempty-method-in-java-with-examples/)

一个 **javax.naming.CompoundName 类**的 **isEmpty()** 方法用于检查这个复合名称对象是否为空。如果一个复合名称没有任何成分，那么它就是空的。

**语法:**

```
public boolean isEmpty()

```

**参数:**此方法不接受任何内容。

**返回值:**如果这个复合名称为空，这个方法返回 true，否则返回 false。

下面的程序说明了 CompoundName.isEmpty()方法:
**程序 1:**

```
// Java program to demonstrate
// CompoundName.isEmpty()

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

        // apply isEmpty()
        boolean isEmpty
            = CompoundName1.isEmpty();

        // print value
        System.out.println("This Compound "
                           + "object is empty:"
                           + isEmpty);
    }
}
```

**Output:**

```
This Compound object is empty:false

```

**程序 2:**

```
// Java program to demonstrate
// CompoundName.isEmpty() method

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
                "", props);

        // apply isEmpty()
        boolean isEmpty
            = CompoundName1.isEmpty();

        // print value
        System.out.println("This Compound "
                           + "object is empty:"
                           + isEmpty);
    }
}
```

**Output:**

```
This Compound object is empty:true

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # isEmpty()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#isEmpty())