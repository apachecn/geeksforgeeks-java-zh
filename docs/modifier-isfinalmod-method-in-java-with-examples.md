# 修饰符是 Java 中的 Final(mod)方法，示例

> 原文:[https://www . geesforgeks . org/modifier-isfinalmod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-isfinalmod-method-in-java-with-examples/)

**是**Java . lang . reflect . modifier**的 Final(mod)** 方法，用于检查整数参数是否包含最终修饰符。如果此整数参数表示最终类型修饰符，则方法返回 true，否则返回 false。

**语法:**

```java
public static boolean isFinal(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含最终修改器，则该方法返回 true 否则为假。

以下程序说明 isFinal()方法:
**程序 1:**

```java
// Java program to illustrate isFinal() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
    {

        // get Method class object
        Method[] methods
            = Shape.class.getMethods();

        // get Modifier Integer value
        int mod = methods[0].getModifiers();

        // check Modifier is final or not
        boolean result = Modifier.isFinal(mod);

        System.out.println("Mod integer value "
                           + mod + " is final : "
                           + result);
    }

    class Shape {

        public final void drawShape() {}
    }
}
```

**Output:**

```java
Mod integer value 17 is final : true

```

**程序 2:**

```java
// Java program to illustrate isFinal()

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

        // check Modifiers are final or not
        boolean result1 = Modifier.isFinal(mod1);
        boolean result2 = Modifier.isFinal(mod2);

        // print results
        System.out.println("Mod integer value "
                           + mod1 + " for method "
                           + methods[0].getName()
                           + " is final : "
                           + result1);

        System.out.println("Mod integer value "
                           + mod2 + " for method"
                           + methods[1].getName()
                           + " is final : "
                           + result2);
    }

    // sample final class
    abstract class Numbers {

        public abstract int initializeNumber();
        public final int declareNumbers()
        {
            return 0;
        }
    }
}
```

**Output:**

```java
Mod integer value 1025 for method initializeNumber is final : false
Mod integer value 17 for methoddeclareNumbers is final : true

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # isFinal(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#isFinal(int))