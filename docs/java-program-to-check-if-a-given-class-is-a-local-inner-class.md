# 检查给定类是否是本地内部类的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序检查给定类是否是本地内部类/](https://www.geeksforgeeks.org/java-program-to-check-if-a-given-class-is-a-local-inner-class/)

[局部内部](https://www.geeksforgeeks.org/local-inner-class-java/)类是在块内声明的类。这些类仅在块内可见。因此，您需要在块中实例化该类。有时，这个块可以用于循环或 if-else 子句。这些类可以访问包含它的类的字段。本地内部类必须在定义它们的块中实例化。

我们将讨论如何使用以下方法来检查给定的类是否是[局部内部类](https://www.geeksforgeeks.org/local-inner-class-java/)。**T3】**

**方法 1:**

*   To check whether this class is a local internal class, java.lang.Class provides a method named [**islocalclass ()** .](https://www.geeksforgeeks.org/class-islocalclass-method-in-java-with-examples/)
*   This method returns true if the given class is local, otherwise it returns false. Note that "isLocalClass ()" is defined in the java.lang.Class class. Therefore, it is necessary to call the "getclass ()" method of the object at **first.**
*   This method returns a Class instance that represents the object class. See the following code—

## Java

```java
// Java program to check if a class is inner
// local class using isLocalClass() method

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        class LocalInnerClass {
            // This is a local inner class
        }
        // Creating a LocalInnerClass object
        LocalInnerClass inner = new LocalInnerClass();

        // Getting the Class instance associated with
        // the class of inner(i.e. LocalInnerClass)
        // which is returned by getClass() method of inner
        Class localClass = inner.getClass();

        // isLocalClass() method of localClass returns true
        // if and only if localClass is a Local Class
        System.out.println(
            "Is inner a local class object? :"
            + localClass.isLocalClass());
    }
}
```

**输出**

```java
Is inner a local class object? :true
```