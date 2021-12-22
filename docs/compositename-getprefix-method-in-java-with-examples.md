# Java 中的 CompositeName getPrefix()方法，带示例

> 原文:[https://www . geesforgeks . org/composite name-get prefix-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-getprefix-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **getPrefix()** 方法用于获取一个复合名称对象，该对象的组件由该复合名称中的组件前缀组成。我们需要停止从这个复合名称对象中提取前缀的位置作为参数传递。返回的复合名称对象和此复合名称对象共享相同的语法。如果我们对这个复合名称进行任何更改，都不会影响返回的名称，反之亦然。

**语法:**

```java
public Name getPrefix(int posn)

```

**参数:**此方法接受 **posn** ，这是要停止的组件的从 0 开始的索引。必须在[0，size()]范围内。

**返回值:**该方法返回一个由[0，posn 范围内索引处的组件组成的复合名称。

**异常:**如果 posn 在指定范围之外，该方法抛出**ArrayIndexOutOfBoundsException**。

下面的程序说明了 CompositeName.getPrefix()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompositeName.getPrefix()

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName(
                "aa/bb/cc/dd/ee/ff");

        // apply getPrefix()
        CompositeName newCompositeName
            = (CompositeName)
                  CompositeName1.getPrefix(2);

        // print value
        System.out.println(
            "New CompositeName Object: "
            + newCompositeName);
    }
}
```

**Output:**

```java
New CompositeName Object: aa/bb

```

**程序 2:**

```java
// Java program to demonstrate
// CompositeName.getPrefix() method

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName(
                "c/e/d/v/a/b/z/y/x/f");

        // apply getPrefix()
        CompositeName newCompositeName
            = (CompositeName)
                  CompositeName1.getPrefix(4);

        // print value
        System.out.println(
            "New CompositeName Object: "
            + newCompositeName);
    }
}
```

**Output:**

```java
New CompositeName Object: c/e/d/v

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # getPrefix(int)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#getPrefix(int))