# 用示例在 Java 中类 getField()方法

> 原文:[https://www . geesforgeks . org/class-getfield-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getfield-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getField()** 方法用于获取该类的指定字段，该字段为公共字段及其成员。方法以字段对象的形式返回此类的指定字段。

**语法:**

```java
public Field getField(String fieldName)
       throws NoSuchFieldException,
              SecurityException

```

**参数:**该方法接受一个参数**字段名**，即要获取的字段。

**返回值:**该方法以 field 对象的形式返回该类的指定**字段**。

**异常**如果找不到指定名称的字段，该方法抛出:

*   **无搜索目标索引；**。
*   **空指针异常**如果名称为空
*   **If there is a safety manager and the safety conditions are not met, the safety is abnormal** .

以下程序演示了 getField()方法。

**例 1:**

```java
// Java program to demonstrate getField() method

import java.util.*;

public class Test {

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException, NoSuchFieldException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        String fieldName = "obj";

        // Get the field of myClass
        // using getField() method
        System.out.println(
            fieldName + " Field of myClass: "
            + myClass.getField(fieldName));
    }
}
```

**输出:**

```java
Class represented by myClass: class Test
obj Field of myClass: public java.lang.Object Test.obj

```

**例 2:**

```java
// Java program to demonstrate getField() method

import java.util.*;

class Main {

    private Object obj;

    Main()
    {

        class Arr {
        };

        obj = new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException, NoSuchFieldException
    {
        Main t = new Main();

        // returns the Class object
        Class myClass = t.obj.getClass();

        String fieldName = "obj";

        try {
            // Get the field of myClass
            // using getField() method
            System.out.println(
                fieldName + " Field of myClass: "
                + myClass.getField(fieldName));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```java
java.lang.NoSuchFieldException: obj

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getField-Java . lang . string-](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getField-java.lang.String-)