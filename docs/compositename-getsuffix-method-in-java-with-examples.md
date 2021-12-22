# Java 中的 CompositeName getSuffix()方法，带示例

> 原文:[https://www . geeksforgeeks . org/composite name-get suffix-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-getsuffix-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **getSuffix()** 方法用于获取一个复合名称对象，该对象的组件由该复合名称中的组件后缀组成。我们需要从这个复合名称对象开始提取后缀的位置作为参数传递。返回的复合名称对象和此复合名称对象共享相同的语法。如果我们对这个复合名称进行任何更改，都不会影响返回的名称，反之亦然。

**语法:**

```
public Name getSuffix(int posn)

```

**参数:**该方法接受**参数**，该参数是从 0 开始的组件索引。必须在[0，size()]范围内。

**返回值:**该方法返回一个由[posn，size()]范围内索引处的组件组成的复合名称。如果 posn 等于 size()，则返回一个空的复合名称。

**异常:**如果 posn 在指定范围之外，该方法抛出**ArrayIndexOutOfBoundsException**。

下面的程序说明了 CompositeName.getSuffix()方法:
**程序 1:**

```
// Java program to demonstrate
// CompositeName.getSuffix()

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
                "0/1/2/3/4/5/6/7/8/9");

        // apply getSuffix()
        CompositeName newCompositeName
            = (CompositeName)
                  CompositeName1.getSuffix(3);

        // print value
        System.out.println("New CompositeName Object: "
                           + newCompositeName);
    }
}
```

**Output:**

```
New CompositeName Object: 3/4/5/6/7/8/9

```

**程序 2:**

```
// Java program to demonstrate
// CompositeName.getSuffix() method

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

        // apply getSuffix()
        CompositeName newCompositeName
            = (CompositeName)
                  CompositeName1.getSuffix(3);

        // print value
        System.out.println(
            "New CompositeName Object: "
            + newCompositeName);
    }
}
```

**Output:**

```
New CompositeName Object: v/a/b/z/y/x/f

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # getSuffix(int)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#getSuffix(int))