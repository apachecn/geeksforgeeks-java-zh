# Java 中的 Field getByte()方法，带示例

> 原文:[https://www . geesforgeks . org/field-getbyte-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getbyte-method-in-java-with-examples/)

**[的 **getByte()** 方法](https://www.geeksforgeeks.org/reflection-in-java/)。字段**用于获取字节的值，字节必须是静态或实例字段类型。当一个类包含一个静态或实例字节字段，并且我们想要得到该字段的值，那么我们可以使用这个方法返回字段的值。

**语法:**

```java
public Byte getByte(Object obj)
            throws IllegalArgumentException,
                   IllegalAccessException

```

**参数:**该方法接受单个参数 **obj** ，该参数是提取字节值的对象。

**返回值:**该方法返回转换为类型字节的字段值。

**异常:**该方法抛出以下异常:

1.  **IllegalAccessException:** 如果 Field 对象正在执行 Java 语言访问控制，并且基础字段不可访问，则会引发此异常。
2.  **IllegalArgumentException:**如果指定的对象不是声明基础字段的类或接口的实例，或者如果字段值不能通过扩展转换转换为类型字节，则会引发此异常。
3.  **NullPointRexception:**如果指定的对象为空，并且该字段是实例字段，则会引发此异常。
4.  **exceptioniniinitializerror:**如果此方法引发的初始化失败，则会引发此异常。

以下程序说明 getByte()方法:
**程序 1:**

```java
// Java program to demonstrate the getByte() method

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

        // Get the identificationByte field object
        Field field
            = User.class
                  .getField("identificationByte");

        // Apply getByte Method on User Object
        // to get the value of identificationByte field
        byte value = field.getByte(user);

        // print result
        System.out.println("Value of Byte Field"
                           + " identificationByte is "
                           + value);

        // Now Get the selectionByte field object
        field = User.class.getField("selectionByte");

        // Apply getByte Method on User Object
        // to get the value of selectionByte field
        value = field.getByte(user);

        // print result
        System.out.println("Value of Byte Field"
                           + " selectionByte is "
                           + value);
    }
}

// sample User class
class User {

    // static Byte values
    public static byte identificationByte = 'E';
    public static byte selectionByte = 121;

    // getter and setter methods
    public static byte getIdentificationByte()
    {
        return identificationByte;
    }

    public static void
    setIdentificationByte(byte identificationByte)
    {
        User.identificationByte = identificationByte;
    }

    public static byte getSelectionByte()
    {
        return selectionByte;
    }
    public static void
    setSelectionByte(byte selectionByte)
    {
        User.selectionByte = selectionByte;
    }
}
```

**Output:**

```java
Value of Byte Field identificationByte is 69
Value of Byte Field selectionByte is 121

```

**程序 2:**

```java
// Java program to demonstrate the getByte() method

import java.lang.reflect.Field;

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException,
               IllegalArgumentException,
               IllegalAccessException
    {

        // Create the Codes class object
        Codes codes = new Codes();

        // Get the value field object
        Field field
            = Codes.class.getField("value");

        // Apply getByte Method on field Object
        // to get the value of value field
        byte value = field.getByte(codes);

        // print result
        System.out.println("Value: " + value);
    }
}
// Codes class
class Codes {
    // Byte field
    public static byte value = 12;
}
```

**Output:**

```java
Value: 12

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # getByte-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#getByte-java.lang.Object-)