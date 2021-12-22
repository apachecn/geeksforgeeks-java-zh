# Java 中的 Class getEnumConstants()方法，带示例

> 原文:[https://www . geesforgeks . org/class-getenumconstats-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getenumconstants-method-in-java-with-examples/)

**[java.lang.Class 类](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/)** 的**getenumconstats()**方法用于获取该类的枚举常量。方法以对象数组的形式返回此类的枚举常量，这些对象构成了此类表示的枚举类。

**语法:**

```
public T[] getEnumConstants()

```

**参数:**该方法不接受任何参数

**返回值:**这个方法以枚举对象数组的形式返回这个类的指定**枚举常量**。

下面的程序演示了 getEnumConstants()方法。

**例 1:**

```
// Java program to demonstrate
// getEnumConstants() method

import java.util.*;

enum A {}

public class Test {

    public Object obj;

    public static void main(String[] args)
    {

        // returns the Class object for this class
        Class myClass = A.class;

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the Enum constants of myClass
        // using getEnumConstants() method
        System.out.println(
            "Enum constants of myClass: "
            + Arrays.toString(
                  myClass.getEnumConstants()));
    }
}
```

**输出:**

```
Class represented by myClass: class A
Enum constants of myClass: []

```

**例 2:**

```
// Java program to demonstrate
// getEnumConstants() method

import java.util.*;

enum A {
    RED,
    GREEN,
    BLUE;
}

class Main {

    private Object obj;

    public static void main(String[] args)
    {

        try {

            // returns the Class object for this class
            Class myClass = A.class;

            System.out.println("Class represented by myClass: "
                               + myClass.toString());

            // Get the Enum constants of myClass
            // using getEnumConstants() method
            System.out.println(
                "Enum constants of myClass: "
                + Arrays.toString(
                      myClass.getEnumConstants()));
        }
        catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

**输出:**

```
Class represented by myClass: class A
Enum constants of myClass: [RED, GREEN, BLUE]

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getenumconstats–](https://docs.oracle.com/javase/9/docs/api/java/lang/Class.html#getEnumConstants--)