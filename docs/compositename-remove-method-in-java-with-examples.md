# 用示例在 Java 中编写 remove()方法

> 原文:[https://www . geesforgeks . org/composite name-remove-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-remove-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **remove()** 方法用于从该复合名称中移除位于 **posn** 位置的组件。位置 **posn** 作为参数传递给该方法。此方法移除位置为“posn”的复合名称对象的组件，并且位置大于“posn”的组件下移一位。对象的大小减少 1。

**语法:**

```
public Object remove(int posn)
       throws InvalidNameException

```

**参数:**此方法接受 **posn** ，这是要删除的组件的索引。必须在[0，size()]范围内。

**返回值:**此方法返回移除的组件(字符串)。

**异常:**如果 posn 在指定范围之外(包括复合名称为空的情况)并且 InvalidNameException 如果删除组件会违反复合名称的语法，此方法将引发**arrayindextofboundsexception**。

下面的程序说明了 CompositeName.remove()方法:
**程序 1:**

```
// Java program to demonstrate
// CompositeName.remove()

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
                "a/b/d/e/g/h/j/k/l");

        // apply remove()
        String removedComponent
            = (String)
                  CompositeName1.remove(5);

        // print value
        System.out.println(
            "Removed Component: "
            + removedComponent);
        System.out.println(
            "CompositeName After removal: "
            + CompositeName1);
    }
}
```

**Output:**

```
Removed Component: h
CompositeName After removal: a/b/d/e/g/j/k/l

```

**程序 2:**

```
// Java program to demonstrate
// CompositeName.remove() method

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
                "aa/bb/cc/dd/ee/ff/gg/hh");

        // apply remove()
        String removedComponent1
            = (String)
                  CompositeName1.remove(1);

        // print value
        System.out.println("Removed Component: "
                           + removedComponent1);
        System.out.println("CompositeName After removal: "
                           + CompositeName1);

        // again remove component
        String removedComponent2
            = (String)
                  CompositeName1.remove(2);

        // print results
        System.out.println(
            "Removed Component: "
            + removedComponent2);
        System.out.println(
            "CompositeName After removal: "
            + CompositeName1);
    }
}
```

**Output:**

```
Removed Component: bb
CompositeName After removal: aa/cc/dd/ee/ff/gg/hh
Removed Component: dd
CompositeName After removal: aa/cc/ee/ff/gg/hh

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # remove(int)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#remove(int))