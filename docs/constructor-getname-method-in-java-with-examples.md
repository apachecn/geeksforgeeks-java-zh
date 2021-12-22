# Java 中的构造函数 getName()方法，带示例

> 原文:[https://www . geesforgeks . org/constructor-getname-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-getname-method-in-java-with-examples/)

[构造器类](https://www.geeksforgeeks.org/constructors-in-java/)提供了关于一个类的单个构造器的信息，并且还提供了对该构造器的访问。
Java . lang . reflect . constructor 的 **getName()** 方法用于以字符串形式返回该构造函数名称。构造函数名称是构造函数的声明类的二进制名称。

**语法:**

```java
public String getName()

```

**参数:**此方法不接受任何内容。

**返回**:该方法以字符串格式返回底层成员的**简单名称**。

以下程序说明 getName()方法:
**程序 1:**

```java
// Java program to illustrate getName() method

import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object array
        // from class object
        Constructor[] con
            s
            = classObj.getConstructors();

        // apply getName method
        System.out.println("Constructor : "
                           + cons[0].getName());
    }
}
```

**Output:**

```java
Constructor : java.lang.String

```

**程序 2:**

```java
// Java program to illustrate getName() method

import java.lang.reflect.Constructor;
import java.util.ArrayList;

public class GFG {

    public static void main(String[] args)
    {
        // get Constructor object for class object
        Constructor constructor
            = ArrayList.class.getConstructors()[0];

        // apply getName method
        String name = constructor.getName();

        // print result
        System.out.println("Constructor Name : "
                           + name);
    }
}
```

**Output:**

```java
Constructor Name : java.util.ArrayList

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # getName(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getName(java.lang.Object))