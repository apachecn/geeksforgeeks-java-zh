# Java 中的 CompositeName size()方法，带示例

> 原文:[https://www . geesforgeks . org/composite name-size-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-size-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **size()** 方法用于返回复合名称对象的大小，该大小等于该复合名称中的组件数量。

**语法:**

```java
public int size()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该组合名称中非负数的组件数。

下面的程序说明了 CompositeName.size()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompositeName.size()

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
                "1/2/3/4/5/6/7/8/9/0");

        // apply size()
        int size = CompositeName1.size();

        // print value
        System.out.println("size: "
                           + size);
    }
}
```

**Output:**

```java
size: 10

```

**程序 2:**

```java
// Java program to demonstrate
// CompositeName.size() method

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
                "c/e/d/v/a/y/x/f");

        // apply size()
        int size = CompositeName1.size();

        // print value
        System.out.println("size:" + size);
    }
}
```

**Output:**

```java
size:8

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # size()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#size())