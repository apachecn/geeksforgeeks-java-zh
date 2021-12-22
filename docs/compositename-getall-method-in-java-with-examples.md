# Java 中的 CompositeName getAll()方法，带示例

> 原文:[https://www . geesforgeks . org/composite name-getall-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-getall-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **getAll()** 方法用于返回这个复合对象的所有组件作为字符串的枚举。应用于此枚举的复合名称的更新效果未定义。

**语法:**

```java
public Enumeration getAll()

```

**参数:**此方法不接受任何内容。

**返回值:**这个方法返回这个复合名称的组件的非空枚举。枚举的每个元素都属于字符串类。

下面的程序说明了 CompositeName.getAll()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompositeName.getAll()

import java.util.Enumeration;
import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName
            = new CompositeName("a/b/z/y/x");

        // apply getAll()
        Enumeration<String> components
            = CompositeName.getAll();

        // print value
        while (components.hasMoreElements()) {
            System.out.println("Component: "
                               + components.nextElement());
        }
    }
}
```

**程序 2:**

```java
// Java program to demonstrate
// CompositeName.getAll() method

import java.util.Enumeration;
import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName
            = new CompositeName("ca/ea/dz/y/x/f");

        // apply getAll()
        Enumeration<String> components
            = CompositeName.getAll();

        // print value
        int i = 0;
        while (components.hasMoreElements()) {
            System.out.println("position "
                               + i + ": "
                               + components.nextElement());
            i++;
        }
    }
}
```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # GetAll()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#getAll())