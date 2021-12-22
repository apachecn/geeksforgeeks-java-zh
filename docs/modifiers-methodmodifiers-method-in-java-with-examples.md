# 修饰符 methodModifiers()方法在 Java 中用示例

> 原文:[https://www . geesforgeks . org/modifiers-method modifiers-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifiers-methodmodifiers-method-in-java-with-examples/)

**java.lang.reflect.Modifier 类**的 **methodModifiers()** 方法用于获取整数值以及可应用于方法的源语言的修饰符。

**语法:**

```
public static boolean methodModifiers()

```

**参数:**此方法不接受任何内容。

**返回**:该方法返回一个**整数值**，将可应用于方法的源语言修饰符组合在一起。

下面的程序举例说明了 methodModifiers()方法:
**程序 1:**

```
// Java program to illustrate
// methodModifiers() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier using methodModifiers()
        int result = Modifier.methodModifiers();

        System.out.println(
            "Method Modifiers: "
            + Modifier.toString(result));
    }
}
```

**Output:**

```
Method Modifiers:
 public protected private abstract
 static final synchronized native strictfp

```

**程序 2:**

```
// Java program to illustrate
// methodModifiers() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier using methodModifiers()
        int result = Modifier.methodModifiers();

        System.out.println("Int Value: "
                           + result);
    }
}
```

**Output:**

```
Int Value: 3391

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # method modifiers()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#methodModifiers--)