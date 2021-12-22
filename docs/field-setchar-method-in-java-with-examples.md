# Java 中的 Field setChar()方法，示例

> 原文:[https://www . geesforgeks . org/field-setchar-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-setchar-method-in-java-with-examples/)

**setChar()** 方法的 **java.lang.reflect.Field** 用于将字段的值设置为指定对象上的一个字符。当需要将对象字段的值设置为字符时，可以使用此方法在对象上设置值。

**语法:**

```java
public void setChar(Object obj, char c)
            throws IllegalArgumentException,
                   IllegalAccessException

```

**参数:**该方法接受两个参数:

*   **obj** :哪个对象的字段应该被修改
*   **c** :是正在修改的 obj 字段的新值。

**返回**:此方法不返回任何内容。

**异常**:该方法抛出如下异常:

*   IllegalAccessException:如果此字段对象正在实施 Java 语言访问控制，并且基础字段是不可访问的或最终的。
*   IllegalArgumentException:如果指定的对象不是声明基础字段(或其子类或实现者)的类或接口的实例，或者如果展开转换失败。
*   NullPointerException:如果指定的对象为空，并且该字段是实例字段。
*   ExceptionInInitializerError:如果此方法引发的初始化失败。

下面的程序说明了 setChar()方法:
**程序 1:**

```java
// Java program to illustrate setByte() method

// program illustrate setChar()
import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create user object
        Employee emp = new Employee();

        // print value of lastNamePrefix
        System.out.println(
            "Value of lastNamePrefix before "
            + "applying setChar is "
            + emp.lastNamePrefix);

        // Get the marks field object
        Field field = Employee.class
                          .getField("lastNamePrefix");

        // Apply setChar Method
        field.setChar(emp, 'B');

        // print value of lastNamePrefix
        System.out.println(
            "Value of lastNamePrefix after "
            + "applying setChar is "
            + emp.lastNamePrefix);

        // print value of firstNamePrefix
        System.out.println(
            "Value of firstNamePrefix before "
            + "applying setChar is "
            + emp.firstNamePrefix);

        // Get the marks field object
        field = Employee.class
                    .getField("firstNamePrefix");

        // Apply setChar Method
        field.setChar(emp, 'Z');

        // print value of firstNamePrefix
        System.out.println(
            "Value of firstNamePrefix after "
            + "applying setChar is "
            + emp.firstNamePrefix);
    }
}

// sample class
class Employee {

    // static char values
    public static char firstNamePrefix = 'A';
    public static char lastNamePrefix = 'S';
}
```

**Output:**

```java
Value of lastNamePrefix before applying setChar is S
Value of lastNamePrefix after applying setChar is B
Value of firstNamePrefix before applying setChar is A
Value of firstNamePrefix after applying setChar is Z

```

**程序 2:**

```java
// Java program to illustrate setChar() method

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

        // Apply setChar Method
        field.setChar(user, 'A');

        // print value of isActive
        System.out.println("Value after "
                           + "applying setChar is "
                           + user.id);
    }
}

// sample User class
class User {

    // static char values
    public static char id = 'Z';
}
```

**Output:**

```java
Value after applying setChar is A

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # setChar-Java . lang . object-char-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#setChar-java.lang.Object-char-)