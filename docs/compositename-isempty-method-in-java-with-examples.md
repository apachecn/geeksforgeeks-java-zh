# Java 中的 CompositeName isEmpty()方法，带示例

> 原文:[https://www . geesforgeks . org/composite name-isempty-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-isempty-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **isEmpty()** 方法用于检查这个复合名称对象是否为空。如果复合名称没有任何组成部分，则称其为空。

**语法:**

```
public boolean isEmpty()

```

**参数:**此方法不接受任何内容。

**返回值:**如果该复合名称为空，则该方法返回 true，否则返回 false。

下面的程序说明了 CompositeName.isEmpty()方法:
**程序 1:**

```
// Java program to demonstrate
// CompositeName.isEmpty()

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName("a/b/z/y/x");

        // apply isEmpty()
        boolean isEmpty
            = CompositeName1.isEmpty();

        // print value
        System.out.println(
            "This composite "
            + "object is empty: " + isEmpty);
    }
}
```

**Output:**

```
This composite object is empty: false

```

**程序 2:**

```
// Java program to demonstrate
// CompositeName.isEmpty() method

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {

    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName("");

        // apply isEmpty()
        boolean isEmpty
            = CompositeName1.isEmpty();

        // print value
        System.out.println(
            "This composite "
            + "object is empty: "
            + isEmpty);
    }
}
```

**Output:**

```
This composite object is empty: true

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # isEmpty()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#isEmpty())