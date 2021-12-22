# 方法类| Java 中的 getDefaultValue()方法

> 原文:[https://www . geesforgeks . org/method-class-getdefaultvalue-method-in-Java/](https://www.geeksforgeeks.org/method-class-getdefaultvalue-method-in-java/)

[java.lang.reflect](https://www.geeksforgeeks.org/reflection-in-java/) 的 **getDefaultValue()** 方法。方法类。它返回由方法对象表示的[注释成员](https://www.geeksforgeeks.org/annotations-in-java/)的默认值。
当注释成员属于原语类型时，该方法返回该[包装类型](https://www.geeksforgeeks.org/wrapper-classes-java/)的实例。如果注释成员不包含任何默认值，或者如果方法对象没有注释类型的成员，则返回 null。

**语法:**

```java
public Object getDefaultValue()
```

**返回值:**此方法返回此 method 对象表示的注释成员的默认值。

**异常:**如果注释的类型为类，并且找不到默认类值的定义，该方法将抛出**类型的 NotPresentException** 。

下面的程序说明了方法类的 getDefaultValue()方法:

**示例 1:** 下面的程序包含一个接口名称演示，其中包含由接口方法表示的注释成员的一些默认值。程序的主方法为接口的每个方法创建方法对象，如果方法包含注释的默认值，则打印注释的默认值。

```java
/*
* Program Demonstrate getDefaultValue() method 
* of Method Class.
*/
import java.lang.reflect.Method;

// Main Class
public class GFG {
    public static void main(String[] args)
        throws NoSuchMethodException, SecurityException
    {

        // Get Method Object
        Method methodObj1 = demo
                                .class
                                .getDeclaredMethod("fauvMovie");

        // Apply getDefaultValue() method
        Object obj1 = methodObj1.getDefaultValue();

        // print default value
        System.out.println(obj1);

        // Get Method Object
        Method methodObj2 = demo
                                .class
                                .getDeclaredMethod("fauvMovieRating");

        // Apply getDefaultValue() method
        Object obj2 = methodObj2.getDefaultValue();

        // print default value
        System.out.println(obj2);

        // Get Method Object
        Method methodObj3 = demo
                                .class
                                .getDeclaredMethod("fauvMovieReleaseYear");

        // Apply getDefaultValue() method
        Object obj3 = methodObj3.getDefaultValue();

        // print default value
        System.out.println(obj3);
    }

    // an interface with default annotations
    public @interface demo {
        public String fauvMovie() default "Inception";
        public double fauvMovieRating() default 9.6;
        public int fauvMovieReleaseYear();
    }
    }
```

**Output:**

```java
Inception
9.6
null

```

**示例 2:** 下面的程序包含一个接口名称演示和一个类名演示，接口名称演示带有由接口方法表示的注释成员的一些默认值，类名演示没有注释的默认值。程序的 Main 方法为接口和类的每个方法创建方法对象，如果方法包含注释的默认值，则打印注释的默认值。

```java
/*
* Program Demonstrate getDefaultValue() method 
* of Method Class.
*/
import java.lang.annotation.*;
import java.lang.reflect.Method;

// a simple class with no annotations
class demo {
    public void demoMethod(String value)
    {
        System.out.println("demo method: " + value);
    }
}

public class GFG {

    // Main method
    public static void main(String[] args)
    {
        try {
            // create class object
            Class classobj = demo.class;
            Class[] parameterTypes = { String.class };

            // get Method Object
            @SuppressWarnings("unchecked")
            Method method = classobj
                                .getMethod("demoMethod",
                                           parameterTypes);

            // Print default value
            System.out.println("default value of demoMethod():"
                               + method.getDefaultValue());

            // get Method Object
            Method methodobj = demoInterface
                                   .class
                                   .getDeclaredMethod("getValue");

            // get default value
            Object defaultValue = methodobj.getDefaultValue();

            // Print default value
            System.out.println("default value of getValue():"
                               + defaultValue);
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    // a interface with some annotation
    @Target({ ElementType.METHOD })
    @Retention(RetentionPolicy.RUNTIME)
    private @interface demoInterface {
        int getValue() default 51;
    }
}
```

**Output:**

```java
default value of demoMethod():null
default value of getValue():51

```

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getDefaultValue–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getDefaultValue--)