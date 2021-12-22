# 修饰符是 Java 中的接口(mod)方法，示例

> 原文:[https://www . geesforgeks . org/modifier-isinterface mod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-isinterfacemod-method-in-java-with-examples/)

**Java . lang . reflect . modifier**的 **isInterface(mod)** 方法用于检查整数参数是否包含接口修饰符。如果此整数参数表示接口类型修饰符，则方法返回 true，否则返回 false。

**语法:**

```
public static boolean isInterface(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含接口修饰符，则该方法返回 true 否则为假。

下面的程序说明了 isInterface()方法:
**程序 1:**

```
// Java program to illustrate isInterface() method

import java.lang.reflect.Modifier;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // get Modifier Integer value
        int mod = Symbols.class.getModifiers();

        // check Modifier is interface or not
        boolean result = Modifier.isInterface(mod);

        System.out.println("Mod integer value "
                           + mod + " is interface : "
                           + result);
    }

    interface Symbols {
        void createSynbols();
    }
}
```

**Output:**

```
Mod integer value 1544 is interface : true

```

**程序 2:**

```
// Java program to illustrate isInterface()

import java.lang.reflect.Modifier;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException
    {

        // get Modifier Integer value
        int mod = Calculator.class.getModifiers();

        // check Modifier is Interface or not
        boolean result = Modifier.isInterface(mod);

        System.out.println("Mod integer value "
                           + mod + " is Interface : "
                           + result);
    }

    abstract class Calculator {
        abstract void addNumbers();
    }
}
```

**Output:**

```
Mod integer value 1024 is Interface : false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # Isinterface(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#isInterface(int))