# Java 中的 Field setInt()方法，示例

> 原文:[https://www . geesforgeks . org/field-setint-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-setint-method-in-java-with-examples/)

**setInt()** 方法的 **java.lang.reflect.Field** 用于在指定对象上将字段的值设置为 Int。当需要将对象字段的值设置为 int 时，可以使用此方法在对象上设置值。

**语法:**

```java
public void setInt(Object obj, int i)
            throws IllegalArgumentException,
                   IllegalAccessException

```

**参数:**该方法接受两个参数:

*   **obj** :哪个对象的字段应该被修改
*   **i** :这是正在修改的 obj 字段的新值。

**返回**:此方法不返回任何内容。

**异常**:该方法抛出如下异常:

*   IllegalAccessException:如果此字段对象正在实施 Java 语言访问控制，并且基础字段是不可访问的或最终的。
*   IllegalArgumentException:如果指定的对象不是声明基础字段(或其子类或实现者)的类或接口的实例，或者如果展开转换失败。
*   NullPointerException:如果指定的对象为空，并且该字段是实例字段。
*   ExceptionInInitializerError:如果此方法引发的初始化失败。

下面的程序说明了 setInt()方法:
**程序 1:**

```java
// Java program to illustrate setInt() method
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
            + "applying setInt is "
            + emp.salary);

        // Get the  field object
        Field field = Employee.class.getField("salary");

        // Apply setInt Method
        field.setInt(emp, 2243599);

        // print value of salary
        System.out.println(
            "Value of salary after "
            + "applying setInt is "
            + emp.salary);

        // print value of uniqueNo
        System.out.println(
            "Value of uniqueNo before "
            + "applying setInt is "
            + emp.uniqueNo);

        // Get the field object
        field = Employee.class.getField("uniqueNo");

        // Apply setInt Method
        field.setInt(emp, 123434);

        // print value of uniqueNo
        System.out.println(
            "Value of uniqueNo after "
            + "applying setInt is "
            + emp.uniqueNo);
    }
}

// sample class
class Employee {

    // static int values
    public static int uniqueNo = 234289;
    public static int salary = 1125213;
}
```

**Output:**

```java
Value of salary before applying setInt is 1125213
Value of salary after applying setInt is 2243599
Value of uniqueNo before applying setInt is 234289
Value of uniqueNo after applying setInt is 123434

```

**程序 2:**

```java
// Java program to illustrate setInt() method

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

        // Apply setInt Method
        field.setInt(no, 53266);

        // print value of isActive
        System.out.println(
            "Value after "
            + "applying setInt is "
            + Numbers.value);
    }
}

// sample Numbers class
class Numbers {

    // static int value
    public static int value = 13685;
}
```

**Output:**

```java
Value after applying setInt is 53266

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # setInt-Java . lang . object-int-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#setInt-java.lang.Object-int-)