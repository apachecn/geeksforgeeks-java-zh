# Java 中修饰符 isAbstract(mod)方法，示例

> 原文:[https://www . geesforgeks . org/modifier-isabstractmod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-isabstractmod-method-in-java-with-examples/)

**Java . lang . reflect . modifier**的 **isAbstract(mod)** 方法用于检查整数参数是否包含抽象修饰符。如果此整数参数表示抽象类型修饰符，则方法返回 true，否则返回 false。

**语法:**

```java
public static boolean isAbstract(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含抽象修饰符，则该方法返回 true 否则为假。

下面的程序说明了 isAbstract()方法:
**程序 1:**

```java
// Java program to illustrate isAbstract() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
    {

        // get Method class object
        Method[] methods
            = Shape.class.getMethods();

        // get Modifier Integer value
        int mod = methods[0].getModifiers();

        // check Modifier is Abstract or not
        boolean result = Modifier.isAbstract(mod);

        System.out.println("Mod integer value "
                           + mod + " is Abstract : "
                           + result);
    }

    abstract class Shape {

        public abstract String drawShape();
    }
}
```

**Output:**

```java
Mod integer value 1025 is Abstract : true

```

**程序 2:**

```java
// Java program to illustrate isAbstract()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
    {

        // get Method class object
        Method[] methods = Numbers.class.getMethods();

        // get Modifier Integer value
        int mod1 = methods[0].getModifiers();
        int mod2 = methods[1].getModifiers();

        // check Modifiers are Abstract or not
        boolean result1 = Modifier.isAbstract(mod1);
        boolean result2 = Modifier.isAbstract(mod2);

        // print results
        System.out.println("Mod integer value "
                           + mod1 + " for method "
                           + methods[0].getName()
                           + " is Abstract : "
                           + result1);

        System.out.println("Mod integer value "
                           + mod2 + " for method"
                           + methods[1].getName()
                           + " is Abstract : "
                           + result2);
    }

    // sample abstract class
    abstract class Numbers {

        public abstract int initializeNumber();
        public final int declareNumbers()
        {
            return 0;
        };
    }
}
```

**Output:**

```java
Mod integer value 1025 for method initializeNumber is Abstract : true
Mod integer value 17 for methoddeclareNumbers is Abstract : false

```

**参考文献:**T2