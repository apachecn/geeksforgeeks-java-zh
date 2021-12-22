# 用 Java 编写 endsWith()方法，示例

> 原文:[https://www . geesforgeks . org/composite name-end swith-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-endswith-method-in-java-with-examples/)

**javax.naming.CompositeName 类**的 **endsWith()** 方法用于检查作为参数传递的复合名称是否是该复合名称的后缀。如果复合名称对象以“X”结尾，则复合名称“X”是该复合名称的后缀。如果 X 为空或者不是复合名称对象，则返回 false。

**语法:**

```java
public boolean endsWith(Name n)

```

**参数:**该方法接受 **n** ，这可能是要检查的空组合名称。

**返回值:**如果 n 是一个复合名，并且是这个复合名的后缀，这个方法返回 true，否则返回 false。

下面的程序说明了 CompositeName.endsWith()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompositeName.endsWith()

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName("1/2/3/4/5/6");
        CompositeName CompositeName2
            = new CompositeName("5/6");

        // apply endsWith()
        boolean endWithFlag
            = CompositeName1.endsWith(CompositeName2);

        // print value
        if (endWithFlag)
            System.out.println("CompositeName1 ends with "
                               + " CompositeName2");
        else
            System.out.println("CompositeName1 not ends with "
                               + " CompositeName2");
    }
}
```

**Output:**

```java
CompositeName1 ends with  CompositeName2

```

**程序 2:**

```java
// Java program to demonstrate
// CompositeName.endsWith() method

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName("c/e/d/v/a/b/z/y/x/f");
        CompositeName CompositeName2
            = new CompositeName("z/y/x");

        // apply endsWith()
        boolean endWithFlag
            = CompositeName1.endsWith(CompositeName2);

        // print value
        if (endWithFlag)
            System.out.println("CompositeName1 ends with "
                               + " CompositeName2");
        else
            System.out.println("CompositeName1 not ends with "
                               + " CompositeName2");
    }
}
```

**Output:**

```java
CompositeName1 not ends with  CompositeName2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # end swith(javax . naming . name)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#endsWith(javax.naming.Name))