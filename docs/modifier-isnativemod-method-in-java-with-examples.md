# 修饰符是 Java 中的一种方法，示例

> 原文:[https://www . geeksforgeeks . org/modifier-is initial mod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-isnativemod-method-in-java-with-examples/)

**Java . lang . reflect . modifier**的**是一种(mod)** 方法，用于检查整数参数是否包含本机修饰符。如果此整数参数表示本机类型修饰符，则方法返回 true 否则返回 false。

**语法:**

```
public static boolean isNative(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含原生修饰符，则该方法返回 true，否则返回 false。

下面的程序说明了 isNative()方法:
**程序 1:**

```
// Java program to illustrate isNative() method

import java.lang.reflect.Method;
import java.lang.reflect.Modifier;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // get Method class object
        Method[] methods
            = Calculator.class.getMethods();

        // get Modifier Integer value
        int mod = methods[0].getModifiers();

        // check Modifier is native or not
        boolean result = Modifier.isNative(mod);

        System.out.println("Mod integer value "
                           + mod + " is native : "
                           + result);
    }

    class Calculator {
        native void addNumbers();
    }
}
```

**Output:**

```
Mod integer value 17 is native : false

```

**程序 2:**

```
// Java program to illustrate isNative()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
    {

        // get Method class object
        Method[] methods
            = Numbers.class.getMethods();

        // get Modifier Integer value
        int mod1 = methods[0].getModifiers();
        int mod2 = methods[1].getModifiers();

        // check Modifiers are native or not
        boolean result1 = Modifier.isNative(mod1);
        boolean result2 = Modifier.isNative(mod2);

        // print results
        System.out.println("Mod integer value "
                           + mod1 + " for method "
                           + methods[0].getName()
                           + " is native : "
                           + result1);

        System.out.println("Mod integer value "
                           + mod2 + " for method"
                           + methods[1].getName()
                           + " is native : "
                           + result2);
    }

    // sample native class
    abstract class Numbers {

        abstract public int initializeNumber();
        int declareNumbers()
        {
            return 0;
        }
    }
}
```

**Output:**

```
Mod integer value 1025 for method initializeNumber is native : false
Mod integer value 17 for methodwait is native : false

```

**参考文献:**T2