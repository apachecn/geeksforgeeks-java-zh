# Java 中的字段设置 Short()方法，示例

> 原文:[https://www . geesforgeks . org/field-set short-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-setshort-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **setShort()** 方法用于将字段的值设置为指定对象上的短值。当需要将对象字段的值设置为短值时，可以使用此方法在对象上设置值。

**语法:**

```
public void setShort(Object obj, short s)
         throws IllegalArgumentException,
                IllegalAccessException

```

**参数:**该方法接受两个参数:

*   **obj** :哪个对象的字段应该被修改
*   **s** :是正在修改的 obj 字段的新值。

**返回**:此方法不返回任何内容。

**异常**:该方法抛出如下异常:

*   **IllegalAccessException** :如果这个 Field 对象正在执行 Java 语言的访问控制，并且基础字段不可访问或者是最终的。
*   **IllegalArgumentException** :如果指定的对象不是声明底层字段的类或接口的实例(或其子类或实现者)，或者如果展开转换失败。
*   **NullPoshorterException** :如果指定对象为空，且字段为实例字段。
*   **exceptioniniinitializerror**:如果这个方法引发的初始化失败。

下面的程序说明了 setShort()方法:
**程序 1:**

```
// Java program to illustrate setShort() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create user object
        Employee emp = new Employee();

        // print value of uniqueNo
        System.out.println(
            "Value of uniqueNo before "
            + "applying setShort is "
            + emp.uniqueNo);

        // Get the field object
        Field field
            = Employee.class
                  .getField("uniqueNo");

        // Apply setShort Method
        field.setShort(emp, (short)134);

        // print value of uniqueNo
        System.out.println(
            "Value of uniqueNo after "
            + "applying setShort is "
            + emp.uniqueNo);
    }
}

// sample class
class Employee {

    // static short values
    public static short uniqueNo = 239;
}
```

**Output:**

```
Value of uniqueNo before applying setShort is 239
Value of uniqueNo after applying setShort is 134

```

**程序 2:**

```
// Java Program to illustrate setShort() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create Numbers object
        Numbers no = new Numbers();

        // Get the value field object
        Field field
            = Numbers.class.getField("value");

        // Apply setShort Method
        field.setShort(no, (short)5366);

        // print value of isActive
        System.out.println(
            "Value after "
            + "applying setShort is "
            + Numbers.value);
    }
}

// sample Numbers class
class Numbers {

    // static short value
    public static short value = 13685;
}
```

**Output:**

```
Value after applying setShort is 5366

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # setShort-Java . lang . object-short-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#setShort-java.lang.Object-short-)