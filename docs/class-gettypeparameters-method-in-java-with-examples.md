# 用示例在 Java 中类 getTypeParameters()方法

> 原文:[https://www . geesforgeks . org/class-gettypeparameters-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-gettypeparameters-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getTypeParameters()** 方法用于获取该实体的类型参数。这个实体可以是类、数组、接口等。方法返回表示类型变量的类型变量对象数组。

**语法:**

```java
public TypeVariable<Class<T>> getTypeParameters()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个表示类型变量的**类型变量**对象数组。

下面的程序演示了 getTypeParameters()方法。

**例 1:**

```java
// Java program to demonstrate getTypeParameters() method

import java.util.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the type parameters of myClass
        // using getTypeParameters() method
        System.out.println(
            "TypeParameters of myClass: "
            + Arrays.toString(
                  myClass.getTypeParameters()));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
TypeParameters of myClass: []

```