# Java 中的 CompositeName compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/composite name-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-compareto-method-in-java-with-examples/)

**javax.naming.CompositeName 类**的 **compareTo()** 方法用于将该 CompositeName 与作为参数传递的指定对象进行比较。它返回一个负整数、零或正整数，因为该组合名称小于、等于或大于给定的对象作为参数。如果传递的对象为空或者不是 CompositeName 的实例，则该方法将引发 ClassCastException。

**语法:**

```
public int compareTo(Object obj)

```

**参数:**该方法接受**对象**，该对象是非空对象进行比较。

**返回值:**此方法返回一个负整数、零或正整数，因为此名称小于、等于或大于给定的对象。

**异常:**
如果 obj 不是 CompositeName，这个方法抛出 ClassCastException。

下面的程序说明了 CompositeName.compareTo()方法:
**程序 1:**

```
// Java program to demonstrate
// CompositeName.compareTo()

import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create Composite name object
        CompositeName compositeName1
            = new CompositeName("x/y");
        CompositeName compositeName2
            = new CompositeName("x/z");

        // apply compareTo()
        int value
            = compositeName1.compareTo(compositeName2);

        // print value
        if (value > 0)
            System.out.println("CompositeName1 is "
                               + "greater than CompositeName2");
        else if (value < 0)
            System.out.println("CompositeName1 is "
                               + "smaller than CompositeName2");
        else
            System.out.println("CompositeName1 is "
                               + " equal to CompositeName2");
    }
}
```

**Output:**

```
CompositeName1 is smaller than CompositeName2

```

**程序 2:**

```
// Java program to demonstrate
// CompositeName.compareTo() method

import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create Composite name object
        CompositeName compositeName1
            = new CompositeName("x/y/z/a");
        CompositeName compositeName2
            = new CompositeName("x/y/x/a");

        // apply compareTo()
        int value
            = compositeName1.compareTo(compositeName2);

        // print value
        if (value > 0)
            System.out.println("CompositeName1 is "
                               + "greater than CompositeName2");
        else if (value < 0)
            System.out.println("CompositeName1 is "
                               + "smaller than CompositeName2");
        else
            System.out.println("CompositeName1 is "
                               + " equal to CompositeName2");
    }
}
```

**Output:**

```
CompositeName1 is greater than CompositeName2

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # compare to(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#compareTo(java.lang.Object))