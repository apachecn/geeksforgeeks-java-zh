# Java 中的 Field getDeclaringClass()方法，带示例

> 原文:[https://www . geesforgeks . org/field-getdeclaringclass-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getdeclaringclass-method-in-java-with-examples/)

**[的 **getDeclaringClass()** 方法](https://www.geeksforgeeks.org/reflection-in-java/)。字段**用于获取声明该字段对象所代表的字段的类对象。如果字段对象存在，并且我们想要获取类对象，那么我们可以使用这个方法获取该类对象。

**语法:**

```
public Class<T> getDeclaringClass()

```

**参数:**此方法不接受任何内容。

**返回值:**该方法返回一个表示基础成员声明类的对象。

下面的程序说明了 getDeclaringClass()方法:
**程序 1:**

```
// Java program to demonstrate the above method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // Get the value field object
        Field field
            = User.class
                  .getField("identificationChar");

        // get the declaring class object
        Class declaringClass
            = field.getDeclaringClass();

        // print result
        System.out.println("Declaring Class"
                           + " for Field Object: "
                           + declaringClass);
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
Declaring Class for Field Object: class User

```

**程序 2:**

```
// Java program to demonstrate the above method

import java.lang.reflect.Field;

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // Get the value field object
        Field field
            = Alphabets.class.getField("value");

        // get the declaring class object
        Class declaringClass
            = field.getDeclaringClass();

        // print result
        System.out.println("Declaring Class: "
                           + declaringClass);
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
Declaring Class: class GFG$Alphabets

```

**参考文献:**