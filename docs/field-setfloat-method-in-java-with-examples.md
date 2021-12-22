# Java 中的 Field setFloat()方法，示例

> 原文:[https://www . geesforgeks . org/field-setfloat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-setfloat-method-in-java-with-examples/)

**setFloat()****Java . lang . reflect . field**的方法，用于将字段的值设置为指定对象上的浮点数。当您需要将对象字段的值设置为浮点数时，可以使用此方法在对象上设置值。

**语法:**

```java
public void setFloat(Object obj, float f)
            throws IllegalArgumentException,
                   IllegalAccessException

```

**参数:**该方法接受两个参数:

*   **obj** :哪个对象的字段应该被修改
*   **f** :是正在修改的 obj 字段的新值。

**返回**:此方法不返回任何内容。

**异常**:该方法抛出如下异常:

*   IllegalAccessException:如果此字段对象正在实施 Java 语言访问控制，并且基础字段是不可访问的或最终的。
*   IllegalArgumentException:如果指定的对象不是声明基础字段(或其子类或实现者)的类或接口的实例，或者如果展开转换失败。
*   NullPointerException:如果指定的对象为空，并且该字段是实例字段。
*   ExceptionInInitializerError:如果此方法引发的初始化失败。

下面的程序说明了 setFloat()方法:
**程序 1:**

```java
// Java program to illustrate setFloat() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create user object
        Employee emp = new Employee();

        // print value of salary
        System.out.println(
            "Value of salary before "
            + "applying setFloat is "
            + emp.salary);

        // Get the marks field object
        Field field = Employee.class.getField("salary");

        // Apply setFloat Method
        field.setFloat(emp, 259939.99f);

        // print value of salary
        System.out.println(
            "Value of salary after "
            + "applying setFloat is "
            + emp.salary);

        // print value of pf
        System.out.println(
            "Value of pf before "
            + "applying setFloat is "
            + emp.pf);

        // Get the marks field object
        field = Employee.class.getField("pf");

        // Apply setFloat Method
        field.setFloat(emp, 234234.34f);

        // print value of pf
        System.out.println(
            "Value of pf after "
            + "applying setFloat is "
            + emp.pf);
    }
}

// sample class
class Employee {

    // static float values
    public static float pf = 122342.89f;
    public static float salary = 143125f;
}
```

**Output:**

```java
Value of salary before applying setFloat is 143125.0
Value of salary after applying setFloat is 259939.98
Value of pf before applying setFloat is 122342.89
Value of pf after applying setFloat is 234234.34

```

**程序 2:**

```java
// Java program to illustrate setFloat() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create Numbers object
        Numbers no = new Numbers();

        // Get the value field object
        Field field = Numbers.class
                          .getField("value");

        // Apply setFloat Method
        field.setFloat(no, 3244.466f);

        // print value of isActive
        System.out.println(
            "Value after "
            + "applying setFloat is "
            + Numbers.value);
    }
}

// sample Numbers class
class Numbers {

    // static float value
    public static float value = 26774.3685f;
}
```

**Output:**

```java
Value after applying setFloat is 3244.466

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # setFloat-Java . lang . object-float-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#setFloat-java.lang.Object-float-)