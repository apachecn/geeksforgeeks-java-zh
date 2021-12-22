# Java 中的 CompoundName remove()方法，示例

> 原文:[https://www . geesforgeks . org/compound name-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-remove-method-in-java-with-examples/)

**javax.naming.CompoundName 类**的 **remove()** 方法用于从该复合名称中移除位于 **posn** 位置的组件。位置 **posn** 作为参数传递给该方法。此方法移除位于“posn”位置的复合名称对象的组件，并且位于大于“posn”位置的组件下移一位。对象的大小减少 1。

**语法:**

```java
public Object remove(int posn)
       throws InvalidNameException

```

**参数:**该方法接受 posn，posn 是要删除的组件的索引。必须在[0，size()]范围内。

**返回值:**此方法返回移除的组件(字符串)。

**异常:**如果 posn 在指定范围之外(包括复合名称为空的情况)并且 InvalidNameException 如果删除组件会违反复合名称的语法，则此方法将引发**arrayindextofboundsexception**。

以下程序说明了 CompoundName.remove()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompoundName.remove()
import java.util.Properties;

import javax.naming.CompoundName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args) throws InvalidNameException
    {

        // need properties for CompoundName
        Properties props = new Properties();
        props.put("jndi.syntax.separator", "@");
        props.put("jndi.syntax.direction",
                  "left_to_right");

        // create compound name object
        CompoundName CompoundName1
            = new CompoundName(
                "0@1@2@3@4@5@6@7",
                props);

        // apply remove()
        String removedComponent
            = (String)
                  CompoundName1.remove(5);

        // print value
        System.out.println(
            "Removed Component: "
            + removedComponent);
        System.out.println(
            "CompoundName After removal:"
            + CompoundName1);
    }
}
```

**Output:**

```java
Removed Component: 5
CompoundName After removal:0@1@2@3@4@6@7

```

**程序 2:**

```java
// Java program to demonstrate
// CompoundName.remove() method
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
                "c/e/d/v/a/b/z/y/x/f", props);

        // apply remove()
        String removedComponent1
            = (String)
                  CompoundName1.remove(1);

        // print value
        System.out.println(
            "Removed Component: "
            + removedComponent1);
        System.out.println(
            "CompoundName After removal:"
            + CompoundName1);

        // again remove component
        String removedComponent2
            = (String)
                  CompoundName1.remove(2);

        // print results
        System.out.println("Removed Component: "
                           + removedComponent2);
        System.out.println("CompoundName After removal:"
                           + CompoundName1);
    }
}
```

**Output:**

```java
Removed Component: e
CompoundName After removal:c/d/v/a/b/z/y/x/f
Removed Component: v
CompoundName After removal:c/d/a/b/z/y/x/f

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # remove(int)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#remove(int))