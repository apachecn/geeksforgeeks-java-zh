# 方法类| Java 中的 getAnnotation()方法

> 原文:[https://www . geesforgeks . org/method-class-getannotation-method-in-Java/](https://www.geeksforgeeks.org/method-class-getannotation-method-in-java/)

方法类的 **[方法返回作为参数传递的指定类型的方法对象的注释(如果存在这样的注释，则为空)。这是获取方法对象注释的重要方法。](https://www.geeksforgeeks.org/reflection-in-java/)**

**语法:**

```
public <T extends Annotation> T getAnnotation(Class<T> annotationClass)
```

**参数:**该方法取一个强制参数*标注类*，它是标注类型的 Class 对象。

**返回值:**此方法返回指定注释类型的方法注释(如果存在于此元素中)，否则为空。

**异常:**如果给定的注释类为空，该方法抛出*空指针异常*

下面的程序说明了方法类的方法:

**示例 1:** 该程序打印指定注释类型的方法注释，该注释类型作为参数提供给表示 GFG 类的 getCustomAnnotation()方法的 method 对象的 getAnnotation()。

在这个例子中，使用了一个单独的类，该类包含两种方法，即主方法和带注释的方法。

```
// Program Demonstrate getAnnotation(Class<T> annotationClass) method
// of Method Class.

import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.reflect.Method;

// create a custom Annotation
@Retention(RetentionPolicy.RUNTIME)
@interface Annotation {

    // This annotation has two attributes.
    public String key();

    public String value();
}

// create the Main Class
public class GFG {

    // call Annotation for method and pass values for annotation
    @Annotation(key = "AvengersLeader", value = "CaptainAmerica")
    public static void getCustomAnnotation()
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

            // get Annotation of Method object m by passing
            // Annotation class object as parameter
            Annotation anno = method.getAnnotation(Annotation.class);

            // print Annotation Details
            System.out.println("Annotation for Method Object"
                               + " having name: " + method.getName());
            System.out.println("Key Attribute of Annotation: "
                               + anno.key());
            System.out.println("Value Attribute of Annotation: "
                               + anno.value());
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
Annotation for Method Object having name: getCustomAnnotation
Key Attribute of Annotation: AvengersLeader
Value Attribute of Annotation: CaptainAmerica

```

**示例 2:** 该程序打印指定注释类型的方法注释，该注释类型作为参数提供给表示 GFG 类的 getCustomAnnotation()方法的 method 对象的 getAnnotation()。

在这个例子中，使用了两个类。一个类包含创建方法对象并应用 getAnnotation()方法的主方法，另一个类包含带有一些注释的方法。

```
// Program Demonstrate getAnnotation(Class<T> annotationClass) method
// of Method Class.

import java.lang.annotation.Retention;
import java.lang.annotation.RetentionPolicy;
import java.lang.reflect.Method;

public class GFG {
    public static void main(String[] args)
    {

        // get array Method objects
        Method[] methods = GFGDemoClass.class.getMethods();

        // get Annotation
        SelfCreatedAnnotation annotation = methods[0]
                                               .getAnnotation(
                                                   SelfCreatedAnnotation
                                                       .class);

        // Print annotation attribute
        System.out.println("key: " + annotation.key());
        System.out.println("value: " + annotation.value());
    }
}

// Another class on which we want to apply the annotation
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

// create custom annotation having two values
@Retention(RetentionPolicy.RUNTIME)
@interface SelfCreatedAnnotation {
    public String key();
    public String value();
}
```

**输出:**

```
key: getField
value: getting field attribute

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getAnnotation-Java . lang . class-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getAnnotation-java.lang.Class-)