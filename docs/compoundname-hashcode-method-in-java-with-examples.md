# Java 中的 CompoundName hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/compound name-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-hashcode-method-in-java-with-examples/)

一个 **javax.naming.CompoundName 类**的 **hashCode()** 方法用来返回这个复合名称的 hash 代码。这个复合名称对象的哈希代码是这个复合名称的单个组件的“规范化”形式的哈希代码的总和。

**语法:**

```
public int hashCode()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回一个表示这个名字的哈希码的 int。

下面的程序说明了 CompoundName.hashCode()方法:
**程序 1:**

```
// Java program to demonstrate
// CompoundName.hashCode()

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

        // apply hashCode()
        int hashCode
            = CompoundName1.hashCode();

        // print value
        System.out.println("hashCode:"
                           + hashCode);
    }
}
```

**Output:**

```
hashCode:558

```

**程序 2:**

```
// Java program to demonstrate
// CompoundName.hashCode() method

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

        // apply hashCode()
        int hashCode
            = CompoundName1.hashCode();

        // print value
        System.out.println("hashCode:"
                           + hashCode);
    }
}
```

**Output:**

```
hashCode:1078

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # hashCode()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#hashCode())