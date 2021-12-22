# Java 中的类 getFields()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getfields-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getfields-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的 **getFields()** 方法用于获取该类的字段，这些字段是公共字段及其成员。方法以字段对象数组的形式返回该类的字段。

**语法:**

```
public Field[] getFields()

```

**参数:**此方法不接受任何参数。

**返回值:**该方法以 Field 对象数组的形式返回该类的**字段**。

**异常**如果有安全经理在场且不满足安全条件，此方法抛出**安全异常**。

下面的程序演示了 getFields()方法。

**例 1:**

```
// Java program to demonstrate getFields() method

import java.util.*;

public class Test {

    public Object obj;

    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the fields of myClass
        // using getFields() method
        System.out.println("Fields of myClass: "
                           + Arrays.toString(
                                 myClass.getFields()));
    }
}
```

**输出:**

```
Class represented by myClass: class Test
Fields of myClass: [public java.lang.Object Test.obj]

```

**例 2:**

```
// Java program to demonstrate getFields() method

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
        throws ClassNotFoundException
    {
        Main t = new Main();

        // returns the Class object
        Class myClass = t.obj.getClass();

        // Get the fields of myClass
        // using getFields() method
        System.out.println("Fields of myClass: "
                           + Arrays.toString(
                                 myClass.getFields()));
    }
}
```

**输出:**

```
Fields of myClass: []

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getFields–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getFields--)