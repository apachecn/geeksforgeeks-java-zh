# 修饰符类修饰符()方法在 Java 中用例子

> 原文:[https://www . geesforgeks . org/modifiers-class modifiers-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifiers-classmodifiers-method-in-java-with-examples/)

**java.lang.reflect.Modifier 类**的 **classModifiers()** 方法用于获取整数值以及可应用于类的源语言的修饰符。

**语法:**

```
public static boolean classModifiers()

```

**参数:**此方法不接受任何内容。

**返回**:这个方法返回一个**整数值**，将可以应用于一个类的源语言修饰符组合在一起。

下面的程序说明了类修饰符()方法:
**程序 1:**

```
// Java program to illustrate
// classModifiers() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier using classModifiers()
        int result = Modifier.classModifiers();

        System.out.println(
            "Modifiers: "
            + Modifier.toString(result));
    }
}
```

**Output:**

```
Modifiers: public protected private abstract static final strictfp

```

**程序 2:**

```
// Java program to illustrate classModifiers()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier using classModifiers()
        int result = Modifier.classModifiers();

        System.out.println("Int Value: "
                           + result);
    }
}
```

**Output:**

```
Int Value: 3103

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # class modifiers()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#classModifiers--)