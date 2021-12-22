# Java 中修饰符接口修饰符()方法示例

> 原文:[https://www . geesforgeks . org/modifiers-interface modifiers-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifiers-interfacemodifiers-method-in-java-with-examples/)

**java.lang.reflect.Modifier 类**的 **interfaceModifiers()** 方法用于获取一个整数值以及可应用于接口的源语言的修饰符。

**语法:**

```
public static boolean interfaceModifiers()

```

**参数:**此方法不接受任何内容。

**返回**:这个方法返回一个 **int 值**，将可以应用于接口的源语言修饰符组合在一起。

下面的程序举例说明了 interfaceModifiers()方法:
**程序 1:**

```
// Java program to illustrate
// interfaceModifiers() method
import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier using interfaceModifiers()
        int result = Modifier.interfaceModifiers();

        System.out.println("Interface Modifiers: "
                           + Modifier.toString(result));
    }
}
```

**Output:**

```
Interface Modifiers: public protected private abstract static strictfp

```

**程序 2:**

```
// Java program to illustrate
// interfaceModifiers()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier
        // using interfaceModifiers()
        int result
            = Modifier.interfaceModifiers();

        System.out.println("Int Value: "
                           + result);
    }
}
```

**Output:**

```
Int Value: 3087

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # interface modifiers()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#interfaceModifiers--)