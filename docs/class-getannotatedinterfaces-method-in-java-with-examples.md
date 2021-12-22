# Java 中的类 getAnnotatedInterfaces()方法，带示例

> 原文:[https://www . geeksforgeeks . org/class-getannotatedinterfaces-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getannotatedinterfaces-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的**GetanNOtatedinterface()**方法用于获取该类中存在的超面类型注释。方法返回存在的注释数组。

**语法:**

```java
public Annotation[] getAnnotatedInterfaces()

```

**参数:**该方法不接受任何参数。

**返回值:**这个方法返回**一个存在的超面类型注释的数组**。

下面的程序演示了 getAnnotatedInterfaces()方法。

**例 1:**

```java
// Java program to demonstrate
// getAnnotatedInterfaces() method

import java.io.*;
import java.util.*;
import java.lang.annotation.*;

// create a custom Annotation
@Retention(RetentionPolicy.RUNTIME)
public @interface CustomInterface {
}

@CustomInterface
interface CustomInterfaceImp {}

class Test implements CustomInterfaceImp{

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println(
            "Class represented by myClass: "
            + myClass.toString());

        // Get the AnnotatedInterfaces 
        // using getAnnotatedInterfaces() method
        System.out.println(
                "AnnotatedInterfaces of myClass: "
            + Arrays.toString(myClass
                .getAnnotatedInterfaces()));
    }
}
```

**输出:**

> 由 myClass 表示的类:class Test
> AnnotatedInterfaces of my class:[sun . reflect . annotation . annotatedtypeffactory $ annotatedtypebaeimpl @ 4a a 298 b 7]

**例 2:**

```java
// Java program to demonstrate
// getAnnotatedInterfaces() method

import java.io.*;
import java.util.*;
import java.lang.annotation.*;

class Test{

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Test.class;

        System.out.println(
            "Class represented by myClass: "
            + myClass.toString());

        // Get the AnnotatedInterfaces
        // using getAnnotatedInterfaces() method
        System.out.println(
                "AnnotatedInterfaces of myClass: "
            + Arrays.toString(myClass
                .getAnnotatedInterfaces()));
    }
}
```

**输出:**

> 由我的类表示的类:类测试
> 注释我的类:[]

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getAnnotatedInterfaces–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getAnnotatedInterfaces--)