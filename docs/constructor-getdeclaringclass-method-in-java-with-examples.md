# Java 中的构造函数 getDeclaringClass()方法，带示例

> 原文:[https://www . geesforgeks . org/constructor-getdeclaringclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-getdeclaringclass-method-in-java-with-examples/)

[构造器类](https://www.geeksforgeeks.org/constructors-in-java/)提供了关于一个类的单个构造器的信息，并且还提供了对该构造器的访问。
Java . lang . reflect . constructor 的 **getDeclaringClass()** 方法用于返回表示声明该对象所表示的构造函数的类的类对象。此方法返回此构造函数的源类的名称。

**语法:**

```java
public Class<T> getDeclaringClass()

```

**参数:**此方法不接受任何内容。

**返回**:这个方法返回一个**对象**，代表底层成员的声明类。

下面的程序说明了 getDeclaringClass()方法:
**程序 1:**

```java
// Java program to illustrate getDeclaringClass() method

import java.lang.reflect.Constructor;

public class Main {

    public static void main(String[] args)
    {

        // get Constructor object array
        // from  String class object
        Constructor[] cons
            = String.class.getConstructors();
        Constructor constructor = cons[0];

        // apply getDeclaringClass method
        Class classObj
            = constructor.getDeclaringClass();

        // print result
        System.out.println("Source class name : "
                           + classObj.getName());
    }
}
```

**Output:**

```java
Source class name : java.lang.String

```

**程序 2:**

```java
// Java program to illustrate getDeclaringClass() method

import java.lang.reflect.Constructor;
import java.util.ArrayList;

public class Main {

    public static void main(String[] args)
    {

        // get Constructor object for class object
        Constructor constructor
            = ArrayList.class.getConstructors()[0];

        // apply getDeclaringClass method
        Class classObj
            = constructor.getDeclaringClass();

        // print result
        System.out.println(
            "Class Name : "
            + classObj.getName());
    }
}
```

**Output:**

```java
Class Name : java.util.ArrayList

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # getDeclaringClass(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getDeclaringClass(java.lang.Object))