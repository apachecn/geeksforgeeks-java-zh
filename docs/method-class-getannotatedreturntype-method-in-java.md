# 方法类| Java 中的 getAnnotatedReturnType()方法

> 原文:[https://www . geeksforgeeks . org/method-class-getannatedreturntype-method-in-Java/](https://www.geeksforgeeks.org/method-class-getannotatedreturntype-method-in-java/)

方法返回一个表示注释类型的注释类型对象来指定方法对象的返回类型。如果方法对象是为构造函数创建的，那么注释类型对象指定构造对象的类型。如果为方法创建了方法对象，则 AnnotatedType 对象指定使用类型来指定源代码中指定的方法的返回类型。

返回的 AnnotatedType 表示 AnnotatedType 本身或其任何子接口(如 AnnotatedArrayType、AnnotatedParameterizedType、AnnotatedTypeVariable、AnnotatedWildcardType)的实现。AnnotatedType 表示任何类型的潜在注释使用，包括数组类型、参数化类型、类型变量或 Java Virtual Machine 中当前运行的通配符类型。

**语法:**

```
public AnnotatedType getAnnotatedReturnType()
```

**返回值:**该方法返回一个 AnnotatedType 对象，该对象代表 AnnotatedType 来指定方法对象的返回类型。

下面的程序说明了方法类的 getAnnotatedReturnType()方法:

**示例 1:** 对于作为输入给出的特定方法，请使用 AnnotatedType()。

该程序包含一个方法名 getAddressMethod，它包含一个注释类型。因此，这个程序将获得包含在 getAddressMethod 方法中的注释类型的细节。

```
// Java program to demonstrate how to
// apply getAnnotatedReturnType() method
// of Method Class.

import java.lang.annotation.*;
import java.lang.reflect.AnnotatedType;
import java.lang.reflect.Method;
import java.util.Arrays;

public class GFG {

    // Creating custom AnnotatedType
    @Target({ ElementType.TYPE_USE })
    @Retention(RetentionPolicy.RUNTIME)
    private @interface customAnnotatedType {
    }

    // a sample method with return type String and
    // AnnotatedType is @customAnnotatedType
    public @customAnnotatedType String getAddress()
    {
        return null;
    }

    // main method
    public static void main(String[] args)
    {

        try {
            // create class object
            Class classobj = GFG.class;

            // create method object of getAddress
            Method getAddressMethod = null;

            Method[] methods = classobj.getMethods();
            for (Method m : methods) {
                if (m.getName().equals("getAddress"))
                    getAddressMethod = m;
            }

            // get AnnotatedType for return type
            AnnotatedType annotatedType = getAddressMethod
                                              .getAnnotatedReturnType();

            // print AnnotatedType details with Method name
            System.out.println("Method Name: "
                               + getAddressMethod.getName());

            System.out.println("Type: "
                               + annotatedType.getType().getTypeName());

            System.out.println("Annotations: "
                               + Arrays.toString(annotatedType.getAnnotations()));
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
Method Name: getAddress
Type: java.lang.String
Annotations: [@GFG$customAnnotatedType()]

```

**示例 2:** 打印 GFG 类方法的数组类型或多维数组或泛型的注释。

```
// Java program to demonstrate how to
// apply getAnnotatedReturnType() method
// of Method Class.

import java.lang.annotation.*;
import java.lang.reflect.*;
import java.util.List;

public class systemUTCMethodDemo<T> {

    // Creating custom AnnotatedType
    @Target({ ElementType.TYPE_USE })
    @Retention(RetentionPolicy.RUNTIME)
    private @interface customAnnotatedType {
    }

    // a sample method with Annotation on array type
    public @customAnnotatedType String[] getAddress()
    {
        return null;
    }

    // a sample method on Annotation on multidimensional array
    public String[] @customAnnotatedType[] getvalues()
    {
        return null;
    }

    // a sample method on Annotation on a type with generic
    public @customAnnotatedType List<T> getWords()
    {
        return null;
    }

    // main method
    public static void main(String[] args)
    {

        try {
            // create class object
            Class classobj = systemUTCMethodDemo.class;

            // create method object of getAddress and getValues
            Method[] methods = classobj.getMethods();

            for (Method m : methods) {

                // if method object is for getAddress and getValues
                // then print @customAnnotatedType for both
                if (m.getName().equals("getAddress")
                    || m.getName().equals("getvalues")
                    || m.getName().equals("getWords")) {
                    printDetails(m);
                }
            }
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }

    public static void printDetails(Method m)
    {

        // get AnnotatedType for return type
        AnnotatedType annotatedType = m.getAnnotatedReturnType();

        // print AnnotatedType details with Method name

        System.out.println("Method Name: " + m.getName());
        System.out.println("Type: " + annotatedType.getType().getTypeName());
        System.out.println("Annotations: " + annotatedType);
        System.out.println();
    }
}
```

**输出:**

```
Method Name: getWords
Type: java.util.List Annotations: sun.reflect.annotation.AnnotatedTypeFactory$AnnotatedParameterizedTypeImpl@12a3a380

Method Name: getvalues
Type: java.lang.String[][]
Annotations: sun.reflect.annotation.AnnotatedTypeFactory$AnnotatedArrayTypeImpl@29453f44

Method Name: getAddress
Type: java.lang.String[]
Annotations: sun.reflect.annotation.AnnotatedTypeFactory$AnnotatedArrayTypeImpl@5cad8086 
```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/annotatedtype . html](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/AnnotatedType.html)