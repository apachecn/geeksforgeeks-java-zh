# Java 中的构造函数 getAnnotatedReceiverType()方法，示例

> 原文:[https://www . geeksforgeeks . org/constructor-getannotedreceivertype-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-getannotatedreceivertype-method-in-java-with-examples/)

**[构造函数](https://www.geeksforgeeks.org/constructors-in-java/)** 类的**GetanNOtatedReceiveType()**方法用于返回一个表示 AnnotatedType 的 AnnotatedType 对象，以指定该构造函数的接收器类型。如果构造函数有一个接收器参数，那么构造函数的接收器类型是可用的。如果此构造函数没有接收器参数，或者有一个接收器参数的类型没有注释，则返回值是一个 AnnotatedType 对象，表示一个没有注释的元素。如果此构造函数是顶级静态成员，则返回值为空。

**语法:**

```
public AnnotatedType getAnnotatedReceiverType()

```

**参数:**此方法不接受任何内容。

**返回值:**此方法返回一个**对象，其类型为“注释类型”**，表示此可执行文件所代表的方法或构造函数的接收器类型，如果此可执行文件不能有接收器参数，则返回空值。

下面的程序说明了 getAnnotatedReceiverType()方法:
**程序 1:**

```
// Java program to demonstrate
// Constructor.getAnnotatedReceiverType() method

import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;
import java.lang.reflect.AnnotatedType;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
        throws NoSuchMethodException
    {

        // create a constructor class
        Constructor<?> c = Test.class.getConstructors()[0];

        // apply getAnnotatedReceiverType()
        AnnotatedType atr
            = c.getAnnotatedReceiverType();

        // print result
        System.out.println(atr);
        System.out.println("Type = "
                           + atr.getType().getTypeName());
    }
}
class Test {
    public Test(@Annotation Test test) {}
}

@Target({ ElementType.TYPE_USE })
@Retention(RetentionPolicy.RUNTIME)
@interface Annotation {
}
```

**Output:**

```
sun.reflect.annotation.AnnotatedTypeFactory$AnnotatedTypeBaseImpl@12a3a380
Type = Test

```

**程序 2:**

```
// Java program to demonstrate
// Constructor.getAnnotatedReceiverType() method

import java.lang.annotation.ElementType;
import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.annotation.Target;
import java.lang.reflect.AnnotatedType;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
        throws NoSuchMethodException
    {

        // create a constructor class
        Constructor<?> c
            = Demo.class.getConstructors()[0];

        // apply getAnnotatedReceiverType()
        AnnotatedType atr
            = c.getAnnotatedReceiverType();

        // print result
        System.out.println(atr);
        System.out.println("Type = "
                           + atr.getType().getTypeName());
    }
}
class Demo {
    public Demo(@PathVar String str) {}
}

@Target({ ElementType.TYPE_USE })
@Retention(RetentionPolicy.RUNTIME)
@interface PathVar {
}
```

**Output:**

```
sun.reflect.annotation.AnnotatedTypeFactory$AnnotatedTypeBaseImpl@12a3a380
Type = Demo

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # getannotatedrereceivertype()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#getAnnotatedReceiverType())