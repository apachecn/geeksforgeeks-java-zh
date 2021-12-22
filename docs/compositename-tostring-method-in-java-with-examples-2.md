# Java 中的 CompositeName toString()方法，带示例

> 原文:[https://www . geesforgeks . org/composite name-tostring-method-in-Java-with-examples-2/](https://www.geeksforgeeks.org/compositename-tostring-method-in-java-with-examples-2/)

一个 **javax.naming.CompositeName 类**的 **toString()** 方法用于创建这个复合名称对象的字符串表示，使用语法“/”作为每个对象的分隔符。此复合名称返回的字符串表示形式包括按顺序枚举此复合名称的每个组件，并用正斜杠“/”字符分隔每个组件。此复合名称对象的空组件由空字符串表示。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回该组合名称的非空字符串表示形式。

下面的程序说明了 CompositeName.toString()方法:
**程序 1:**

```java
// Java program to demonstrate
// CompositeName.toString()

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create a composite name object
        CompositeName CompositeName1
            = new CompositeName(
                "a/n/cc/aa/@@/##/7");

        // apply toString()
        String toString = CompositeName1.toString();

        // print value
        System.out.println("toString: " + toString);
    }
}
```

**Output:**

```java
toString: a/n/cc/aa/@@/##/7

```

**程序 2:**

```java
// Java program to demonstrate
// CompositeName.toString() method

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create a composite name object
        CompositeName CompositeName1
            = new CompositeName("cc/ee/dd/vv/a/b/z/y/x/f");

        // apply toString()
        String toString = CompositeName1.toString();

        // print value
        System.out.println("CompositeName:" + toString);
    }
}
```

**Output:**

```java
CompositeName:cc/ee/dd/vv/a/b/z/y/x/f

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # toString()](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#toString())