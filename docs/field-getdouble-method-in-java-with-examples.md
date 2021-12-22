# Java 中的 Field getDouble()方法，示例

> 原文:[https://www . geesforgeks . org/field-getdouble-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getdouble-method-in-java-with-examples/)

**getDouble()** 法的 **[爪哇岛](https://www.geeksforgeeks.org/reflection-in-java/)。字段**用于获取 double 的值，该值必须是静态或实例字段类型。此方法还用于通过加宽转换获取可转换为双精度类型的另一个基元类型的值。当一个类包含一个静态或实例双字段，并且我们想要得到该字段的值，那么我们可以使用这个方法返回字段的值。

**语法:**

```
public double getDouble(Object obj)
              throws IllegalArgumentException,
                     IllegalAccessException

```

**参数:**该方法接受单个参数 **obj** ，该参数是提取双值的对象。

**返回值:**该方法返回转换为双精度类型的字段值。

**异常:**该方法抛出以下异常:

1.  **IllegalAccessException:** 如果 Field 对象正在执行 Java 语言访问控制，并且基础字段不可访问，则会引发此异常。
2.  **IllegalArgumentException:**如果指定的对象不是声明基础字段的类或接口的实例，或者如果字段值不能通过扩展转换转换为类型 double，则会引发此异常。
3.  **NullPointRexception:**如果指定的对象为空，并且该字段是实例字段，则会引发此异常。
4.  **exceptioniniinitializerror:**如果此方法引发的初始化失败，将引发此异常。

下面的程序说明 getDouble()方法:
**程序 1:**

```
// Java program to demonstrate the getDouble() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException,
               IllegalArgumentException,
               IllegalAccessException
    {

        // Create the User class object
        User user = new User();

        // Get the marks field object
        Field field = User.class.getField("Marks");

        // Apply getDouble Method on User Object
        // to get the value of Marks field
        double value = field.getDouble(user);

        // print result
        System.out.println("Value of double Field"
                           + " Marks is " + value);

        // Now Get the Fees field object
        field = User.class.getField("Fees");

        // Apply getDouble Method on User Object
        // to get the value of Fees field
        value = field.getDouble(user);

        // print result
        System.out.println("Value of double Field"
                           + " Fees is " + value);
    }
}

// sample User class
class User {

    // static double values
    public static double Marks = 34.13;
    public static double Fees = 3413.99;
    public static String name = "Aman";

    public static double getMarks()
    {
        return Marks;
    }

    public static void setMarks(double marks)
    {
        Marks = marks;
    }

    public static double getFees()
    {
        return Fees;
    }

    public static void setFees(double fees)
    {
        Fees = fees;
    }

    public static String getName()
    {
        return name;
    }

    public static void setName(String name)
    {
        User.name = name;
    }
}
```

**Output:**

```
Value of double Field Marks is 34.13
Value of double Field Fees is 3413.99

```

**程序 2:**

```
// Java program to demonstrate the getDouble() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException,
               IllegalArgumentException,
               IllegalAccessException
    {

        // Create the RealNumbers class object
        RealNumbers real = new RealNumbers();

        // Get the value field object
        Field field
            = RealNumbers.class
                  .getField("value");

        // Apply getDouble Method on field Object
        // to get the value of value field
        double value = field.getDouble(real);

        // print result
        System.out.println("Value: " + value);
    }

    // RealNumbers class
    static class RealNumbers {

        // double field
        public static double value
            = 9999999.34567;

        // getter and setter methods
        public static double getValue()
        {
            return value;
        }

        public static void setValue(double value)
        {
            RealNumbers.value = value;
        }
    }
}
```

**Output:**

```
Value: 9999999.34567

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # getDouble-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#getDouble-java.lang.Object-)