# Java 中的方法类| getModifiers()方法

> 原文:[https://www . geesforgeks . org/method-class-getmodifiers-method-in-Java/](https://www.geeksforgeeks.org/method-class-getmodifiers-method-in-java/)

方法类的 **[方法返回该方法对象表示的方法的修饰符。它返回 int 值。然后使用修饰符类，获取对应于该值的修饰符的名称。](https://www.geeksforgeeks.org/reflection-in-java/)**

**语法:**

```java
public int getModifiers()
```

**返回值:**该方法返回该方法对象表示的方法的**修改器**。

下面的程序说明了方法类的 getModifiers()方法:

**程序 1:** 当在类的方法对象上应用 getModifiers()时，该程序打印方法的修饰符。

```java
// Program Demonstrate how to apply getModifiers() method
// of Method Class.

import java.lang.reflect.Method;
import java.lang.reflect.Modifier;

public class GFG {

    // Main method
    public static void main(String[] args)
    {

        try {
            // create class object
            Class classobj = demo.class;

            // get object of setValue() method of demo class
            Method[] methods = classobj.getMethods();
            Method setValueMethodObject = methods[0];

            // get modifier of setValueMethodObject
            int modifier = setValueMethodObject.getModifiers();

            // print modifier details
            System.out.println("Modifier of setValue():");
            System.out.println(Modifier.toString(modifier));
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    // sample class contains method with public modifier
    class demo {
        // method has public modifier
        public int setValue()
        {
            System.out.println("setValue");
            return 24;
        }
    }
}
```

**输出:**

```java
Modifier of setValue():
public

```

**程序 2:** 程序演示如何应用方法类的 getModifiers()方法。程序打印演示类的所有方法的修饰符名称。

```java
// Program Demonstrate how to apply getModifiers() method
// of Method Class.

import java.lang.reflect.Method;
import java.lang.reflect.Modifier;

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = democlass.class;

            // get list of methods of democlass
            Method[] methods = classobj.getMethods();

            // loop through methods list
            for (Method method : methods) {

                // get Modifier of current method
                int modifier = method.getModifiers();

                // print method name
                System.out.println("Modifier of method name:" 
+ method.getName());

                // print Modifier details
                System.out.println(Modifier.toString(modifier));
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
// a simple class
class democlass {

    // method has static modifier
    public static int method1()
    {
        System.out.println("setValue");
        return 24;
    }

    // method has public final modifier
    public final String method2()
    {
        System.out.println("getValue");
        return "getValue";
    }
}
```

**输出:**

```java
Modifier of method name:method1
public static
Modifier of method name:method2
public final
Modifier of method name:wait
public final
Modifier of method name:wait
public final native
Modifier of method name:wait
public final
Modifier of method name:equals
public
Modifier of method name:toString
public
Modifier of method name:hashCode
public native
Modifier of method name:getClass
public final native
Modifier of method name:notify
public final native
Modifier of method name:notifyAll
public final native

```

*解释:*这个程序的输出还显示了方法对象的结果，而不是类对象中定义的方法，如 wait、equals、toString、hashCode、getClass、notifyAll。这些方法是通过类对象从 java.lang lang 包的超类名 Object 继承而来的。

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getModifiers–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getModifiers--)