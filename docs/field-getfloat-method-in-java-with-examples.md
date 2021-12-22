# Java 中的 Field getFloat()方法，示例

> 原文:[https://www . geesforgeks . org/field-getfloat-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getfloat-method-in-java-with-examples/)

**[的 **getFloat()** 方法](https://www.geeksforgeeks.org/reflection-in-java/)。字段**用于获取浮点值，必须是静态或实例字段类型。此方法还用于通过扩展转换获取另一个可转换为类型 float 的基元类型的值。当一个类包含一个静态或实例浮动字段，并且我们想要得到该字段的值，那么我们可以使用这个方法返回字段的值。

**语法:**

```java
public float getFloat(Object obj)
             throws IllegalArgumentException,
                    IllegalAccessException

```

**参数:**该方法接受单个参数 **obj** ，该参数是提取浮点值的对象。

**返回值:**该方法返回转换为类型 float 的字段的值。

**异常:**该方法抛出以下异常:

1.  **IllegalAccessException:** 如果 Field 对象正在执行 Java 语言访问控制，并且基础字段不可访问，则会引发此异常。
2.  **IllegalArgumentException:**如果指定的对象不是声明基础字段的类或接口的实例，或者如果字段值不能通过扩展转换转换为类型 float，则会引发此异常。
3.  **NullPointRexception:**如果指定的对象为空，并且该字段是实例字段，则会引发此异常。
4.  **exceptioniniinitializerror:**如果此方法引发的初始化失败，将引发此异常。

以下程序说明 getFloat()方法:
**程序 1:**

```java
// Java program to demonstrate the getFloat() method

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

        // Apply getFloat Method on User Object
        // to get the value of Marks field
        float value = field.getFloat(user);

        // print result
        System.out.println("Value of float Field"
                           + " Marks is " + value);

        // Now Get the Fees field object
        field = User.class.getField("Fees");

        // Apply getFloat Method on User Object
        // to get the value of Fees field
        value = field.getFloat(user);

        // print result
        System.out.println("Value of float Field"
                           + " Fees is " + value);
    }
}

// sample User class
class User {

    // static float values
    public static float Marks = 94.13f;
    public static float Fees = 1343413.99f;
    public static String name = "Aman";

    public static float getMarks()
    {
        return Marks;
    }

    public static void setMarks(float marks)
    {
        Marks = marks;
    }

    public static float getFees()
    {
        return Fees;
    }

    public static void setFees(float fees)
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

```java
Value of float Field Marks is 94.13
Value of float Field Fees is 1343414.0

```

**程序 2:**

```java
// Java program to demonstrate the getFloat() method

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

        // Apply getFloat Method on field Object
        // to get the value of value field
        float value = field.getFloat(real);

        // print result
        System.out.println("Value: " + value);
    }

    // RealNumbers class
    static class RealNumbers {

        // float field
        public static float value
            = 123432123.1234f;

        // getter and setter methods
        public static float getValue()
        {
            return value;
        }

        public static void setValue(float value)
        {
            RealNumbers.value = value;
        }
    }
}
```

**Output:**

```java
Value: 1.2343212E8

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # getFloat-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#getFloat-java.lang.Object-)