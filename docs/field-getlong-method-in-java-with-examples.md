# Java 中的 Field getLong()方法，带示例

> 原文:[https://www . geesforgeks . org/field-getlong-method-in-Java-with-examples/](https://www.geeksforgeeks.org/field-getlong-method-in-java-with-examples/)

**java.lang.reflect.Field** 的 **getLong()** 方法用于获取 Long 的值，该值必须是静态或实例字段类型。此方法还用于通过扩展转换获取可转换为 long 类型的另一个基元类型的值。当一个类包含一个静态或实例长字段，并且我们想要得到该字段的值，那么我们可以使用这个方法返回字段的值。

**语法:**

```java
public long getLong(Object obj)
             throws IllegalArgumentException,
                    IllegalAccessException

```

**参数:**该方法接受单个参数 **obj** ，该参数是提取长值的对象。

**返回值:**该方法返回转换为 long 类型的字段的值。

**异常:**该方法抛出以下异常:

1.  **IllegalAccessException:** 如果 Field 对象正在执行 Java 语言访问控制，并且底层字段不可访问。
2.  **IllegalArgumentException:**如果指定的对象不是声明基础字段的类或接口的实例，或者字段值不能通过扩展转换转换为 long 类型。
3.  **NullPointRexception:**如果指定的对象为空，并且该字段是实例字段。
4.  **exceptioniniinitializerror:**如果此方法引发的初始化失败。

下面的程序说明了 getLong()方法:
**程序 1:**

```java
// Java program to demonstrate getLong() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Create the User class object
        User user = new User();

        // Get the marks field object
        Field field
            = User.class.getField("HighScore");

        // Apply getLong Method on User Object
        // to get the value of HighScore field
        long value = field.getLong(user);

        // print result
        System.out.println("Value of long Field"
                           + " HighScore is " + value);
    }
}

// sample User class
class User {

    // static long values
    public static long HighScore = 341313432299133L;
    public static String name = "Aman";

    public static long getHighScore()
    {
        return HighScore;
    }

    public static void setHighScore(long HighScore)
    {
        User.HighScore = HighScore;
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
Value of long Field HighScore is 341313432299133

```

**程序 2:**

```java
// Java program to demonstrate getLong() method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws Exception
    {

        // Create the Numbers class object
        Numbers numbers = new Numbers();

        // Get the value field object
        Field field
            = Numbers.class.getField("value");

        // Apply getLong Method on field Object
        // to get the value of value field
        long value = field.getLong(numbers);

        // print result
        System.out.println("Value: " + value);
    }

    // Numbers class
    static class Numbers {

        // long field
        public static long value = 9999994567L;

        // getter and setter methods
        public static long getValue()
        {
            return value;
        }

        public static void setValue(long value)
        {
            Numbers.value = value;
        }
    }
}
```

**Output:**

```java
Value: 9999994567

```

**参考文献:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/field . html # getLong-Java . lang . object-](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Field.html#getLong-java.lang.Object-)