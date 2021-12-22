# Java 中的类 getModifiers()方法，示例

> 原文:[https://www . geesforgeks . org/class-getmodifiers-method-in-Java-with-examples/](https://www.geeksforgeeks.org/class-getmodifiers-method-in-java-with-examples/)

[**java.lang.Class 类**](https://www.geeksforgeeks.org/java-lang-class-class-java-set-1/) 的 **getModifiers()** 方法用于获取该类的 java 语言修饰符。方法返回一个整数，表示此类的编码修饰符。
**语法:**

```
public int getModifiers()
```

**参数:**此方法不接受任何参数。
**返回值:**这个方法返回一个**整数**代表这个类的编码修饰符。
下面的程序演示了 getModifiers()方法。
**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate getModifiers() method

import java.util.*;
import java.lang.reflect.*;

public class Test {
    public static void main(String[] args)
        throws ClassNotFoundException
    {

        // returns the Class object for this class
        Class myClass = Class.forName("Test");

        System.out.println("Class represented by myClass: "
                           + myClass.toString());

        // Get the modifiers of myClass
        // using getModifiers() method
        System.out.println(
            "Modifiers of myClass: "
            + Modifier.toString(
                  myClass.getModifiers()));
    }
}
```

**Output:** 

```
Class represented by myClass: class Test
Modifiers of myClass: public
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate getModifiers() method

import java.util.*;
import java.lang.reflect.*;

class Main {

    private class Arr {
    };

    public Object obj;

    Main()
    {

        obj = new Arr();
    }

    public static void main(String[] args)
        throws ClassNotFoundException
    {
        Main t = new Main();

        // returns the Class object
        Class myClass = t.obj.getClass();

        // Get the modifiers of myClass
        // using getModifiers() method
        System.out.println("Modifiers of myClass: "
                           + Modifier.toString(
                                 myClass.getModifiers()));
    }
}
```

**Output:** 

```
Modifiers of myClass: private
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/lang/class . html # getModifiers–T4】