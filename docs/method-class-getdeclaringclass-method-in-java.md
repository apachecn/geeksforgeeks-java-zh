# 方法类| Java 中的 getDeclaringClass()方法

> 原文:[https://www . geesforgeks . org/method-class-getdeclaringclass-method-in-Java/](https://www.geeksforgeeks.org/method-class-getdeclaringclass-method-in-java/)

Method 类的 **[方法返回类或接口的 Class 对象，该类或接口定义了我们在其上应用这个 getDeclaringClass()方法的方法。](https://www.geeksforgeeks.org/reflection-in-java/)**

**语法:**

```
public Class<?> getDeclaringClass()
```

**返回值:**该方法返回声明该方法的**类对象**。

下面的程序说明了方法类的 getDeclaringClass()方法:

**程序 1:** 通过应用 getDeclaringClass()方法，找到定义该方法的类对象的详细信息。

在下面的程序中，用一些方法创建了一个演示类。创建类对象后，通过调用类对象的 getMethods()函数创建方法对象列表。然后它们在列表中循环，并打印每个方法的声明类的细节。
这个程序的输出还显示了方法对象的结果，而不是类对象中定义的方法，如 wait、equals、toString、hashCode、getClass、notify 和 notifyAll。这些方法是通过类对象从 java.lang 包的超类 Object 继承而来的。

```
// Program Demonstrate getDeclaringClass() method
// of Method Class.

import java.lang.reflect.Method;

// sample class containing some method
class GFGDemoClass {

    // create attributes
    private String field1;
    private String field2;

    // create methods
    public String getField1()
    {
        return field1;
    }
    public void setField1(String field1)
    {
        this.field1 = field1;
    }
    public String getField2()
    {
        return field2;
    }
    public void setField2(String field2)
    {
        this.field2 = field2;
    }
}

// class containing the Main method
public class GFG {
    public static void main(String[] args)
    {

        // get array Method objects of GFGDemoClass
        Method[] methods = GFGDemoClass.class.getMethods();

        // print getDeclaringclass for every Method object
        // looping through a list of method objects
        for (Method m : methods) {

            // get a class object which declares the current method
            // by declaringClass() method
            Class declaringClass = m.getDeclaringClass();

            // print Method name and class name
            System.out.println("Method Name: " + m.getName());
            System.out.println("Declaring class Name: "
                               + declaringClass.getName());
        }
    }
}
```

**Output:**

```
Method Name: getField1
Declaring class Name: GFGDemoClass
Method Name: setField1
Declaring class Name: GFGDemoClass
Method Name: getField2
Declaring class Name: GFGDemoClass
Method Name: setField2
Declaring class Name: GFGDemoClass
Method Name: wait
Declaring class Name: java.lang.Object
Method Name: wait
Declaring class Name: java.lang.Object
Method Name: wait
Declaring class Name: java.lang.Object
Method Name: equals
Declaring class Name: java.lang.Object
Method Name: toString
Declaring class Name: java.lang.Object
Method Name: hashCode
Declaring class Name: java.lang.Object
Method Name: getClass
Declaring class Name: java.lang.Object
Method Name: notify
Declaring class Name: java.lang.Object
Method Name: notifyAll
Declaring class Name: java.lang.Object

```

**程序 2:** 要查找 Object 类方法的细节，通过应用 getDeclaringClass()方法。

```
// Program Demonstrate getDeclaringClass() method
// of Method Class.

import java.lang.reflect.Method;

// sample class containing some method
class BasicOperations {

    // create attributes
    int a;
    int b;

    // create methods
    public int add()
    {
        return a + b;
    }

    public int multiply()
    {
        return a * b;
    }

    public int subtract()
    {
        return a - b;
    }

    public int division()
    {
        return a / b;
    }
}

public class GFG {
    public static void main(String[] args)
    {

        // get array Method objects
        Method[] methods = BasicOperations.class.getMethods();

        // print getDeclaringclass for every Method object
        for (Method m : methods) {

            // get class object by declaringClass() method
            Class declaringClass = m.getDeclaringClass();

            // checks whether the method belong to
            // BasicOperations class or not
            // and if yes then print method name
            // along with declaring class name.
            if (declaringClass.getName().equals("BasicOperations")) {

                // print Method name and class name
                System.out.println("Method Name: " + m.getName());
                System.out.println("Declaring class Name: "
                                   + declaringClass.getName());
            }
        }
    }
}
```

**Output:**

```
Method Name: multiply
Declaring class Name: BasicOperations
Method Name: subtract
Declaring class Name: BasicOperations
Method Name: division
Declaring class Name: BasicOperations
Method Name: add
Declaring class Name: BasicOperations

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getDeclaringClass–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getDeclaringClass--)