# Java 中的 Field setDouble()方法，示例

> 原文:[https://www . geesforgeks . org/field-set double-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-setdouble-method-in-java-with-examples/)

**setDouble()****Java . lang . reflect . field**的方法，用于将字段的值设置为指定对象上的双精度值。当需要将对象字段的值设置为双精度时，可以使用此方法在对象上设置值。

**语法:**

```
public void setDouble(Object obj, double d)
            throws IllegalArgumentException,
                   IllegalAccessException

```

**参数:**该方法接受两个参数:

*   **obj** :哪个对象的字段应该被修改
*   **d** :是正在修改的 obj 字段的新值。

**返回**:此方法不返回任何内容。

**异常**:该方法抛出如下异常:

*   IllegalAccessException:如果此字段对象正在实施 Java 语言访问控制，并且基础字段是不可访问的或最终的。
*   IllegalArgumentException:如果指定的对象不是声明基础字段(或其子类或实现者)的类或接口的实例，或者如果展开转换失败。
*   NullPointerException:如果指定的对象为空，并且该字段是实例字段。
*   ExceptionInInitializerError:如果此方法引发的初始化失败。

下面的程序说明了 setDouble()方法:
**程序 1:**

```
// Java program to illustrate setDouble() method

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
            + "applying setDouble is "
            + emp.salary);

        // Get the field object
        Field field = Employee.class
                          .getField("salary");

        // Apply setDouble Method
        field.setDouble(emp, 50000.99);

        // print value of salary
        System.out.println(
            "Value of salary after "
            + "applying setDouble is "
            + emp.salary);

        // print value of pf
        System.out.println(
            "Value of pf before "
            + "applying setDouble is "
            + emp.pf);

        // Get the field object
        field = Employee.class.getField("pf");

        // Apply setDouble Method
        field.setDouble(emp, 1234.34);

        // print value of pf
        System.out.println(
            "Value of pf after "
            + "applying setDouble is "
            + emp.pf);
    }
}

// sample class
class Employee {

    // static double values
    public static double pf = 2342.89;
    public static double salary = 43125;
}
```

**Output:**

```
Value of salary before applying setDouble is 43125.0
Value of salary after applying setDouble is 50000.99
Value of pf before applying setDouble is 2342.89
Value of pf after applying setDouble is 1234.34

```

**程序 2:**

```
// Java program to illustrate setDouble() method

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

        // Apply setDouble Method
        field.setDouble(no, 53245.466);

        // print value of isActive
        System.out.println(
            "Value after "
            + "applying setDouble is "
            + Numbers.value);
    }
}

// sample Numbers class
class Numbers {

    // static double value
    public static double value = 1232.3685;
}
```

**Output:**

```
Value after applying setDouble is 53245.466

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # setDouble-Java . lang . object-double-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#setDouble-java.lang.Object-double-)