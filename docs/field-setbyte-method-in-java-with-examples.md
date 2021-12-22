# Java 中的字段设置字节()方法，示例

> 原文:[https://www . geesforgeks . org/field-set byte-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-setbyte-method-in-java-with-examples/)

**setByte()** 方法的 **java.lang.reflect.Field** 用于将字段的值设置为指定对象上的一个字节。当需要将对象字段的值设置为字节时，可以使用此方法在对象上设置值。

**语法:**

```
public void setByte(Object obj, byte b)
            throws IllegalArgumentException,
                   IllegalAccessException

```

**参数:**该方法接受两个参数:

*   **obj** :哪个对象的字段应该被修改
*   **b** :是正在修改的 obj 字段的新值。

**返回**:此方法不返回任何内容。

**异常**:该方法抛出如下异常:

*   IllegalAccessException:如果此字段对象正在实施 Java 语言访问控制，并且基础字段是不可访问的或最终的。
*   IllegalArgumentException:如果指定的对象不是声明基础字段(或其子类或实现者)的类或接口的实例，或者如果展开转换失败。
*   NullPointerException:如果指定的对象为空，并且该字段是实例字段。
*   ExceptionInInitializerError:如果此方法引发的初始化失败。

下面的程序说明了 setByte()方法:
**程序 1:**

```
// Java program to illustrate setByte() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create user object
        Employee emp = new Employee();

        // print value of leaveLeft
        System.out.println(
            "Value of leaveLeft before "
            + "applying setByte is "
            + emp.leaveLeft);

        // Get the marks field object
        Field field
            = Employee.class
                  .getField("leaveLeft");

        // Apply setByte Method
        field.setByte(emp, (byte)2);

        // print value of leaveLeft
        System.out.println(
            "Value of leaveLeft after "
            + "applying setByte is "
            + emp.leaveLeft);

        // print value of age
        System.out.println(
            "Value of age before "
            + "applying setByte is "
            + emp.age);

        // Get the marks field object
        field = Employee.class.getField("age");

        // Apply setByte Method
        field.setByte(emp, (byte)56);

        // print value of age
        System.out.println(
            "Value of age after "
            + "applying setByte is "
            + emp.age);
    }
}

// sample class
class Employee {

    // static byte values
    public static byte age = 45;
    public static byte leaveLeft = 12;
}
```

**Output:**

```
Value of leaveLeft before applying setByte is 12
Value of leaveLeft after applying setByte is 2
Value of age before applying setByte is 45
Value of age after applying setByte is 56

```

**程序 2:**

```
// Java program to illustrate setByte() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create user object
        User user = new User();

        // Get the id field object
        Field field = User.class
                          .getField("id");

        // Apply setByte Method
        field.setByte(user, (byte)20);

        // print value of isActive
        System.out.println(
            "Value after "
            + "applying setByte is "
            + user.id);
    }
}

// sample User class
class User {

    // static byte values
    public static byte id = 2;
}
```

**Output:**

```
Value after applying setByte is 20

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # setByte-Java . lang . object-byte-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#setByte-java.lang.Object-byte-)