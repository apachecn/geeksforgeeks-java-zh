# Java 中的 CompositeName get()方法，示例

> 原文:[https://www . geesforgeks . org/composite name-get-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-get-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **get()** 方法用于获取这个复合名称对象的一个组件。作为参数传递的位置，该参数用于从复合名称对象中获取出现在该位置的组件。

**语法:**

```java
public String get(int posn)

```

**参数:**此方法接受 **posn** ，这是要检索的组件的基于 0 的索引。必须在[0，size()]范围内。

**返回值:**该方法返回索引 posn 处的组件。

**异常:**如果 posn 在指定范围之外，该方法抛出**ArrayIndexOutOfBoundsException**。

下面的程序说明了 CompositeName.get()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompositeName.get()

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args) throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName(
                "a/baz/ay/x");

        // apply get()
        String comp1 = CompositeName1.get(0);
        String comp2 = CompositeName1.get(3);

        // print value
        System.out.println(comp1);
        System.out.println(comp2);
    }
}
```

**Output:**

```java
a
x

```

**程序 2:**

```java
// Java program to demonstrate
// CompositeName.get() method

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

        // apply get()
        String pos3 = CompositeName1.get(3);
        String pos4 = CompositeName1.get(4);

        // print value
        System.out.println(
            "Component at position 3: "
            + pos3);
        System.out.println(
            "Component at position 4: "
            + pos4);
    }
}
```

**Output:**

```java
Component at position 3: v
Component at position 4: a

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # get(int)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#get(int))