# Java 中的字段集()方法，示例

> 原文:[https://www . geesforgeks . org/field-set-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-set-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **set()** 方法用于将指定对象参数上该 Field 对象表示的字段值设置为作为参数传递的指定新值。如果基础字段具有基本类型，新值将自动展开。如果字段是静态的，obj 参数将被忽略；它可能为空。否则，基础字段是实例字段。

*   根据不同的情况，此方法会引发不同的异常，例如，如果指定的对象参数为空，此方法会引发 NullPointerException
*   如果指定的对象参数不是声明基础字段的类或接口的实例，则为 IllegalArgumentException。
*   如果此字段对象正在实施 Java 语言访问控制，并且基础字段不可访问，则此方法将引发 IllegalAccessException。
*   此方法引发一个 IllegalArgumentException。如果基础字段是基元类型，将尝试展开转换，将新值转换为基元类型的值。
*   如果这次尝试失败。如果在可能的解包之后，新值无法通过标识或扩展转换转换为基础字段的类型，则此方法将引发 IllegalArgumentException。
*   如果该字段是静态的，并且尚未初始化，则声明该字段的类将被初始化。该字段被设置为可能展开和加宽的新值。如果该字段隐藏在 obj 类型中，则根据前面的规则设置该字段的值。

**语法:**

```java
public void set(Object obj, Object value)
         throws IllegalArgumentException,
                IllegalAccessException

```

**参数:**该方法接受两个参数:

*   **obj** :哪个对象的字段应该被修改
*   **值**:正在修改的 obj 字段的新值。

**返回**:此方法不返回任何内容。

**异常**:该方法抛出如下异常:

*   **IllegalAccessException** :如果这个 Field 对象正在执行 Java 语言的访问控制，并且基础字段不可访问或者是最终的。
*   **IllegalArgumentException** :如果指定的对象不是声明底层字段的类或接口的实例(或其子类或实现者)，或者如果展开转换失败。
*   **NullPointRexception**:如果指定对象为空，且字段为实例字段。
*   **exceptioniniinitializerror**:如果这个方法引发的初始化失败。

以下程序举例说明设置()方法:
**程序 1:**

```java
// Java program illustrate set() method

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
            + "applying set is "
            + emp.uniqueNo);

        // Get the field object
        Field field
            = Employee.class
                  .getField("uniqueNo");

        // Apply set Method
        field.set(emp, (short)1213);

        // print value of uniqueNo
        System.out.println(
            "Value of uniqueNo after "
            + "applying set is "
            + emp.uniqueNo);

        // print value of salary
        System.out.println(
            "Value of salary before "
            + "applying set is "
            + emp.salary);

        // Get the field object
        field = Employee.class.getField("salary");

        // Apply set Method
        field.set(emp, 324344.2323);

        // print value of salary
        System.out.println(
            "Value of salary after "
            + "applying set is "
            + emp.salary);
    }
}

// sample class
class Employee {

    // static values
    public static short uniqueNo = 239;
    public static double salary = 121324.13333;
}
```

**Output:**

```java
Value of uniqueNo before applying set is 239
Value of uniqueNo after applying set is 1213
Value of salary before applying set is 121324.13333
Value of salary after applying set is 324344.2323

```

**程序 2:**

```java
// Java program illustrate set() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws AccessException
    {

        // create attributes object
        attributes att = new attributes();

        // Get the value field object
        Field field1
            = attributes.class
                  .getField("bolValue");
        Field field2
            = attributes.class
                  .getField("intValue");
        Field field3
            = attributes.class
                  .getField("doubleValue");

        // Apply set Method
        field1.set(att, false);
        field2.set(att, 1213);
        field3.set(att, 342414.131);

        // print value of isActive
        System.out.println(
            "Values after "
            + "applying set are { "
            + att.bolValue + ", "
            + att.intValue
            + ", " + att.doubleValue
            + " }.");
    }
}

// sample attributes class
class attributes {

    // static value value
    public static boolean bolValue = false;
    public static int intValue = 13134;
    public static double doubleValue = 1314.141;
}
```

**Output:**

```java
Values after applying set are { false, 1213, 342414.131 }

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # set-Java . lang . object-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#set-java.lang.Object-java.lang.Object-)