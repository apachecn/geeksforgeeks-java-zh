# Java 中的构造函数 getTypeParameters()方法，带示例

> 原文:[https://www . geesforgeks . org/constructor-gettypeparameters-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-gettypeparameters-method-in-java-with-examples/)

**构造函数**类的 **getTypeParameters()** 方法用于获取由该构造函数对象声明的类型变量对象的数组，按声明顺序排列。数组元素表示方法声明的类型变量对象。如果方法对象泛型声明不包含类型变量，则 getTypeParameters()将返回长度为 0 的数组。

**语法:**

```java
public TypeVariable<Constructor<T>>[] getTypeParameters()

```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个类型变量对象的**数组，表示这个泛型声明所声明的类型变量。**

**异常:**如果此泛型声明的泛型签名不符合 Java 虚拟机规范中指定的格式，此方法将引发**泛型签名格式错误**。

下面的程序说明了 getTypeParameters()方法:

**节目 1:**

```java
// Java program to demonstrate
// Constructor.getTypeParameters() method

import java.lang.reflect.Constructor;
import java.lang.reflect.TypeVariable;

public class GFG {

    public static void main(String... args)
        throws NoSuchMethodException
    {

        // Create Test class
        Class<Test> cls = Test.class;

        // Create Constructor Object
        Constructor[] constructors
            = cls.getConstructors();

        // get Annotation array
        TypeVariable[] typeVariables
            = constructors[0].getTypeParameters();

        System.out.println("TypeVariables:"
                           + typeVariables);
    }
}
class Test<N extends Number> {
    public Test(N n) {}
}
```

**输出:**

```java
TypeVariables:[Ljava.lang.reflect.TypeVariable;@15db9742

```

**节目 2:**

```java
// Java program to demonstrate
// Constructor.getTypeParameters() method

import java.lang.reflect.TypeVariable;

public class GFG {

    public static void main(String... args)
    {

        // get Type Parameters
        TypeVariable<Class<GFG_Demo> >[] typeParameters
            = GFG_Demo.class.getTypeParameters();

        // print result
        for (TypeVariable<Class<GFG_Demo> >
                 typeParameter : typeParameters) {
            System.out.println(typeParameter);
        }
    }

    private static class GFG_Demo<N, E> {
    }
}
```

**输出:**

```java
N
E

```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # getTypeParameters()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getTypeParameters())