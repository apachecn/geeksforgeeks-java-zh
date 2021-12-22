# Java 中的字段设置布尔()方法，示例

> 原文:[https://www . geesforgeks . org/field-set boolean-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-setboolean-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **setBoolean()** 方法，用于将字段的值设置为指定对象上的布尔值。当需要将对象字段的值设置为布尔值时，可以使用此方法在对象上设置值。

**语法:**

```java
public void setBoolean(Object obj, boolean z)
            throws IllegalArgumentException,
                   IllegalAccessException

```

**参数:**该方法接受两个参数:

*   **obj** :哪个对象的字段应该被修改
*   **z** :这是正在修改的 obj 字段的新值。

**返回值:**此方法不返回任何内容。

**异常:**该方法抛出以下异常:

*   **IllegalAccessException** :如果这个 Field 对象正在执行 Java 语言的访问控制，并且基础字段不可访问或者是最终的。
*   **IllegalArgumentException** :如果指定的对象不是声明底层字段的类或接口的实例(或其子类或实现者)，或者如果展开转换失败。
*   **NullPointRexception**:如果指定对象为空，且字段为实例字段。
*   **exceptioniniinitializerror**:如果这个方法引发的初始化失败。

下面的程序说明了 setBoolean()方法:
**程序 1:**

```java
// Java program to illustrate setBoolean() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create user object
        User user = new User();

        // print value of isActive
        System.out.println("Value before "
                           + "applying setBoolean is "
                           + user.isActive);

        // Get the marks field object
        Field field
            = User.class
                  .getField("isActive");

        // Apply setBoolean Method
        field.setBoolean(field, false);

        // print result
        System.out.println("Value after "
                           + "applying setBoolean is "
                           + user.isActive);
    }
}

// sample User class
class User {

    // static boolean values
    public static boolean isActive = true;
}
```

**Output:**

```java
Value before applying setBoolean is true
Value after applying setBoolean is false

```

**程序 2:**

```java
// Java program to illustrate setBoolean() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create user object
        Employee emp = new Employee();

        // print value of isManager
        System.out.println("Value of isManager before "
                           + "applying setBoolean is "
                           + emp.isManager);

        // Get the marks field object
        Field field
            = Employee.class
                  .getField("isManager");

        // Apply setBoolean Method
        field.setBoolean(emp, false);

        // print value of isActive
        System.out.println("Value of isPresent before "
                           + "applying setBoolean is "
                           + emp.isManager);

        // print value of isManager
        System.out.println("Value of isManager before "
                           + "applying setBoolean is "
                           + emp.isPresent);

        // Get the marks field object
        field = Employee.class
                    .getField("isPresent");

        // Apply setBoolean Method
        field.setBoolean(emp, true);

        // print value of isActive
        System.out.println("Value of isPresent before "
                           + "applying setBoolean is "
                           + emp.isPresent);
    }
}

// sample User class
class Employee {

    // static boolean values
    public static boolean isPresent = false;
    public static boolean isManager = true;
}
```

**Output:**

```java
Value of isManager before applying setBoolean is true
Value of isPresent before applying setBoolean is false
Value of isManager before applying setBoolean is false
Value of isPresent before applying setBoolean is true

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # setBoolean-Java . lang . object-boolean-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#setBoolean-java.lang.Object-boolean-)