# Java 中的 Field getChar()方法，示例

> 原文:[https://www . geesforgeks . org/field-getchar-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getchar-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getChar()** 方法用于获取 Char 的值，该值必须是静态或实例字段类型。此方法还用于通过扩展转换获取可转换为 char 类型的另一个基元类型的值。当一个类包含一个静态或实例 Char 字段，并且我们想要得到该字段的值，那么我们可以使用这个方法返回 field 的值。

**语法:**

```
public char getChar(Object obj)
       throws IllegalArgumentException,
              IllegalAccessException

```

**参数:**该方法接受单个参数 **obj** ，该参数是从中提取字符值的对象。

**返回值:**该方法返回转换为 char 类型的字段的值。

**异常:**该方法抛出以下异常:

1.  **IllegalAccessException:** 如果 Field 对象正在执行 Java 语言访问控制，并且基础字段不可访问，则会引发此异常。
2.  **IllegalArgumentException:**如果指定的对象不是声明基础字段的类或接口的实例，或者如果字段值无法通过扩展转换转换为 char 类型，则会引发此异常。
3.  **NullPointRexception:**如果指定的对象为空，并且该字段是实例字段，则会引发此异常。
4.  **exceptioniniinitializerror:**如果此方法引发的初始化失败，则会引发此异常。

以下程序说明 getChar()方法:
**程序 1:**

```
// Java program to demonstrate the above method

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

        // Get the identificationChar field object
        Field field
            = User.class.getField("identificationChar");

        // Apply getChar Method on User Object
        // to get the value of identificationChar field
        char value = field.getChar(user);

        // print result
        System.out.println("Value of Char Field"
                           + " identificationChar is "
                           + value);

        // Now Get the selectionChar field object
        field = User.class.getField("selectionChar");

        // Apply getChar Method on User Object
        // to get the value of selectionChar field
        value = field.getChar(user);

        // print result
        System.out.println("Value of Char Field"
                           + " selectionChar is "
                           + value);
    }
}

// sample User class
class User {

    // static char values
    public static char identificationChar = 'E';
    public static char selectionChar = 'A';
    public static String name = "Aman";

    // getter and setter methods
    public static char getIdentificationChar()
    {
        return identificationChar;
    }

    public static void
    setIdentificationChar(char identificationChar)
    {
        User.identificationChar = identificationChar;
    }

    public static char getSelectionChar()
    {
        return selectionChar;
    }

    public static void
    setSelectionChar(char selectionChar)
    {
        User.selectionChar = selectionChar;
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
Value of Char Field identificationChar is E
Value of Char Field selectionChar is A

```

**程序 2:**

```
// Java program to demonstrate the above method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException,
               IllegalArgumentException,
               IllegalAccessException
    {

        // Create the Alphabets class object
        Alphabets alphabet = new Alphabets();

        // Get the value field object
        Field field
            = Alphabets.class.getField("value");

        // Apply getChar Method on field Object
        // to get the value of value field
        char value = field.getChar(alphabet);

        // print result
        System.out.println("Value: " + value);
    }

    // Alphabets class
    static class Alphabets {

        // char field
        public static char value = 'Q';

        // getter and setter methods
        public static char getValue()
        {
            return value;
        }

        public static void setValue(char value)
        {
            Alphabets.value = value;
        }
    }
}
```

**Output:**

```
Value: Q

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # getChar-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#getChar-java.lang.Object-)