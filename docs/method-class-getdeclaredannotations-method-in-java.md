# 方法类| Java 中的 getDeclaredAnnotations()方法

> 原文:[https://www . geesforgeks . org/method-class-getdeclaredannotations-method-in-Java/](https://www.geeksforgeeks.org/method-class-getdeclaredannotations-method-in-java/)

Method 类的**[Java . lang . reflect](https://www.geeksforgeeks.org/reflection-in-java/). Method . getdeclaredannotations()**方法返回只在方法上声明的注释，忽略方法继承的注释。如果方法上没有直接声明的注释，则返回的注释数组为空。对返回数组的修改不会影响返回给其他调用方的数组。当被不同的调用者调用时，所有返回的注释数组都是相互独立的。

**语法:**

```
public Annotation[] getDeclaredAnnotations()
```

**返回值:**这个方法返回一个直接出现在这个元素上的注释数组

下面的程序说明了方法类的 getDeclaredAnnotations()方法:

**程序 1:** 此程序打印仅在方法上声明的注释，并忽略方法对象上使用 getDeclaredAnnotations()方法继承的注释。

```
// Program Demonstrate getDeclaredAnnotations()
// method of Method Class.

import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.reflect.Method;
import java.lang.annotation.Annotation;

// create a custom Annotation
@Retention(RetentionPolicy.RUNTIME)
@interface customAnnotation {

    // This annotation has two attributes.
    public String key();

    public String value();
}

// create the Main Class
public class GFG {

    // call Annotation for method and
    // pass values for annotation
    @customAnnotation(key = "AvengersLeader",
                      value = "CaptainAmerica")
    public static void
    getCustomAnnotation()
    {

        try {

            // create class object for class name GFG
            Class c = GFG.class;

            // get method name getCustomAnnotation as Method object
            Method[] methods = c.getMethods();
            Method method = null;
            for (Method m : methods) {
                if (m.getName().equals("getCustomAnnotation"))
                    method = m;
            }

            // get an array of Annotations
            Annotation[] annotation = method.getDeclaredAnnotations();

            // get annotation from the array of annotation
            // and print the details
            for (Annotation a : annotation) {

                customAnnotation self = (customAnnotation)a;
                // Print annotation attribute
                System.out.println("Annotation details");
                System.out.println("key: " + self.key());
                System.out.println("value: " + self.value());
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    // create main method
    public static void main(String args[])
    {
        getCustomAnnotation();
    }
}
```

**输出:**

```
Annotation details
key: AvengersLeader
value: CaptainAmerica

```

**程序 2:** 该程序只打印在方法上声明的注释，忽略通过在其他类的方法对象上使用 getDeclaredAnnotations()方法继承的注释。

在这个程序中有两个不同的类。一个类包含带有注释的方法，另一个类包含主方法。在主方法中，创建包含注释的其他类的方法的方法对象。在使用 getDeclaredAnnotations()方法创建方法对象之后，只收集在方法上声明的注释，并且在收集注释之后，Info 程序正在打印结果。

```
// Program Demonstrate getDeclaredAnnotations() method
// of Method Class.

import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.reflect.Method;
import java.lang.annotation.Annotation;

// create custom annotation having two values
@Retention(RetentionPolicy.RUNTIME)
@interface SelfCreatedAnnotation {
    public String key();
    public String value();
}

// Another class on which we want to apply an annotation
class GFGDemoClass {
    private String field;

    // create annotation
    @SelfCreatedAnnotation(key = "getField",
                           value = "getting field attribute")
    public String
    getField()
    {
        return field;
    }
}

public class GFG {
    public static void main(String[] args)
    {

        // get array Method objects
        Method[] methods = GFGDemoClass.class.getMethods();

        // get array of Annotations
        Annotation[] annotation = methods[0]
                                      .getDeclaredAnnotations();

        // get annotation from the array of annotation
        // and print the details
        for (Annotation a : annotation) {

            SelfCreatedAnnotation self = (SelfCreatedAnnotation)a;
            // Print annotation attribute

            System.out.println("key: " + self.key());
            System.out.println("value: " + self.value());
        }
    }
}
```

**输出:**

```
key: getField
value: getting field attribute

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getDeclaredAnnotations–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getDeclaredAnnotations--)