# 修饰符参数修饰符()方法在 Java 中的示例

> 原文:[https://www . geesforgeks . org/modifiers-parameter modifiers-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifiers-parametermodifiers-method-in-java-with-examples/)

**java.lang.reflect.Modifier 类**的 **parameterModifiers()** 方法用于获取整数值以及可应用于参数的源语言的修饰符。

**语法:**

```
public static boolean parameterModifiers()

```

**参数:**此方法不接受任何内容。

**返回**:该方法返回一个**整数值**，将可应用于参数的源语言修饰符组合在一起。

下面的程序说明了 parameterModifiers()方法:
**程序 1:**

```
// Java program to illustrate
// parameterModifiers() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier
        // using parameterModifiers()
        int result
            = Modifier.parameterModifiers();

        System.out.println(
            "Modifiers: "
            + Modifier.toString(result));
    }
}
```

**Output:**

```
Modifiers: final

```

**程序 2:**

```
// Java program to illustrate parameterModifiers()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier using parameterModifiers()
        int result = Modifier.parameterModifiers();

        System.out.println("Int Value: "
                           + result);
    }
}
```

**Output:**

```
Int Value: 16

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # parameter modifiers()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#parameterModifiers--)