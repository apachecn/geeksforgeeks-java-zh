# Java 中的 Field getBoolean()方法，带示例

> 原文:[https://www . geesforgeks . org/field-get boolean-in-Java-method-with-examples/](https://www.geeksforgeeks.org/field-getboolean-method-in-java-with-examples/)

**getBoolean()** 法的 **[爪哇国的](https://www.geeksforgeeks.org/reflection-in-java/)。字段**类用于获取类中包含的静态或实例布尔字段的值。当一个类包含一个静态或实例布尔字段，并且我们想要得到该字段的值，那么我们可以使用这个方法返回字段的值。

**语法:**

```java
public boolean getBoolean(Object obj)
               throws IllegalArgumentException,
                      IllegalAccessException

```

**参数:**该方法接受单个参数 **obj** ，该参数是要从中提取布尔值的对象。

**返回值:**该方法返回所需的**布尔字段**的值。

**异常:**该方法抛出以下异常:

1.  **IllegalAccessException:** 如果 Field 对象正在执行 Java 语言访问控制，并且基础字段不可访问，则会引发此异常。
2.  **IllegalArgumentException:**如果指定的对象不是声明基础字段的类或接口的实例，或者如果字段值不能通过扩展转换转换为布尔类型，则会引发此异常。
3.  **NullPointRexception:**如果指定的对象为空，并且该字段是实例字段，则会引发此异常。
4.  **exceptioniniinitializerror:**如果此方法引发的初始化失败，则会引发此异常。

下面的程序说明 getBoolean()方法:
**程序 1:**

```java
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

        // Get the isEmployee field object
        Field field = User.class.getField("isEmployee");

        // Apply getBoolean Method on User Object
        // to get the value of isEmployee field
        boolean value = field.getBoolean(user);

        // print result
        System.out.println("Value of Boolean Field"
                           + " isEmployee is " + value);

        // Now Get the isActive field object
        field = User.class.getField("isActive");

        // Apply getBoolean Method on User Object
        // to get the value of isActive field
        value = field.getBoolean(user);

        // print result
        System.out.println("Value of Boolean Field"
                           + " isActive is " + value);
    }
}

// sample User class
class User {

    // static boolean values
    public static boolean isEmployee = true;
    public static boolean isActive = false;

    public static boolean isEmployee()
    {
        return isEmployee;
    }
    public static void setEmployee(boolean isEmployee)
    {
        User.isEmployee = isEmployee;
    }
    public static boolean isActive()
    {
        return isActive;
    }
    public static void setActive(boolean isActive)
    {
        User.isActive = isActive;
    }
}
```

**Output:**

> 布尔字段的值为真
> 布尔字段的值为假

**程序 2:**

```java
// Java program to demonstrate the above method

import java.lang.reflect.Field;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException,
               IllegalArgumentException,
               IllegalAccessException
    {

        // Create the mathDigit class object
        mathDigit math = new mathDigit();

        // Get the isEmployee field object
        Field field = mathDigit.class.getField("isZero");

        // Apply getBoolean Method on field Object
        // to get the value of isZero field
        boolean value = field.getBoolean(math);

        // print result
        System.out.println("Value: " + value);
    }

    // mathDigit class
    static class mathDigit {

        public static boolean isZero = false;
        public int number;

        public static boolean isZero()
        {
            return isZero;
        }
        public static void setZero(boolean isZero)
        {
            mathDigit.isZero = isZero;
        }
        public int getNumber()
        {
            return number;
        }
        public void setNumber(int number)
        {
            this.number = number;
        }
    }
}
```

**Output:**

> 值:假

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/field . html # getBoolean(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Field.html#getBoolean(java.lang.Object))