# Java 中的 CompoundName size()方法，带示例

> 原文:[https://www . geesforgeks . org/compound name-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-size-method-in-java-with-examples/)

**javax.naming.CompoundName 类**的 **size()** 方法用于返回复合名称对象的大小，该大小等于该复合名称中的组件数量。

**语法:**

```
public int size()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该复合名称中非负数的组件数。

以下程序说明了 CompoundName.size()方法:
**程序 1:**

```
// Java program to demonstrate
// CompoundName.size()

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

        // apply size()
        int size = CompoundName1.size();

        // print value
        System.out.println("size: "
                           + size);
    }
}
```

**Output:**

```
size: 5

```

**程序 2:**

```
// Java program to demonstrate
// CompoundName.size() method

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

        // apply size()
        int size = CompoundName1.size();

        // print value
        System.out.println("size:" + size);
    }
}
```

**Output:**

```
size:9

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # size()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#size())