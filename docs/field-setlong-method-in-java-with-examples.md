# Java 中的 Field setLong()方法，带示例

> 原文:[https://www . geesforgeks . org/field-setlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-setlong-method-in-java-with-examples/)

**setLong()** 方法的 **java.lang.reflect.Field** 用于在指定对象上将字段的值设置为 Long。当需要设置对象字段的值时，可以使用此方法在对象上设置值。

**语法:**

```java
public void setLong(Object obj, long l)
            throws IllegalArgumentException,
                   IllegalAccessException

```

**参数:**该方法接受两个参数:

*   **obj** :哪个对象的字段应该被修改
*   **l** :是正在修改的 obj 字段的新值。

**返回**:此方法不返回任何内容。

**异常**:该方法抛出如下异常:

*   IllegalAccessException:如果此字段对象正在实施 Java 语言访问控制，并且基础字段是不可访问的或最终的。
*   IllegalArgumentException:如果指定的对象不是声明基础字段(或其子类或实现者)的类或接口的实例，或者如果展开转换失败。
*   NullPolongerException:如果指定的对象为空，并且该字段是实例字段。
*   ExceptionInInitializerError:如果此方法引发的初始化失败。

下面的程序说明了 setLong()方法:
**程序 1:**

```java
// Java program to illustrate setLong() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // create user object
        Employee emp = new Employee();

        // print value of salary
        System.out.prlongln(
            "Value of salary before "
            + "applying setLong is "
            + emp.salary);

        // Get the  field object
        Field field = Employee.class.getField("salary");

        // Apply setLong Method
        field.setLong(emp, 10000000);

        // print value of salary
        System.out.prlongln(
            "Value of salary after "
            + "applying setLong is "
            + emp.salary);

        // prlong value of uniqueNo
        System.out.prlongln(
            "Value of uniqueNo before "
            + "applying setLong is "
            + emp.uniqueNo);

        // Get the field object
        field = Employee.class.getField("uniqueNo");

        // Apply setLong Method
        field.setLong(emp, 200000);

        // prlong value of uniqueNo
        System.out.prlongln(
            "Value of uniqueNo after "
            + "applying setLong is "
            + emp.uniqueNo);
    }
}

// sample class
class Employee {

    // static long values
    public static long uniqueNo = 234289;
    public static long salary = 1125213;
}
```

**Output:**

```java
Value of salary before applying setLong is 1234567
Value of salary after applying setLong is 10000000
Value of uniqueNo before applying setLong is 234289
Value of uniqueNo after applying setLong is 2000000

```

**程序 2:**

```java
// Java program to illustrate setLong() method

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

        // Apply setLong Method
        field.setLong(no, 36283435);

        // prlong value of isActive
        System.out.prlongln(
            "Value after "
            + "applying setLong is "
            + Numbers.value);
    }
}

// sample Numbers class
class Numbers {

    // static long value
    public static long value = 121314454;
}
```

**Output:**

```java
Value after applying setLong is 36283435

```

**参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # setLong-Java . lang . object-long-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#setLong-java.lang.Object-long-)