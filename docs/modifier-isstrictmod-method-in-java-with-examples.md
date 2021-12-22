# 修饰符是 Java 中的一个方法，示例

> 原文:[https://www . geesforgeks . org/modifier-isstrictmod-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifier-isstrictmod-method-in-java-with-examples/)

**java.lang.reflect .修饰符**的 **isStrict(mod)** 方法用于检查整数参数是否包含 strictfp 修饰符。如果此整数参数表示 strictfp 类型修饰符，则方法返回 true 否则返回 false。

**语法:**

```
public static boolean isStrict(int mod)

```

**参数:**该方法接受整数名称，因为 mod 表示一组修饰符。

**返回**:如果 mod 包含 strictfp 修饰符，则该方法返回 true 否则为假。

以下程序说明 isStrict()方法:
**程序 1:**

```
// Java program to illustrate isStrict() method
import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier Integer value
        int mod = Test.class.getModifiers();

        // check Modifier is strict or not
        boolean result = Modifier.isStrict(mod);

        System.out.println("Mod integer value "
                           + mod + " is strict : "
                           + result);
    }

    strictfp class Test {
        strictfp double mul()
        {
            return 0;
        }
    }
}
```

**Output:**

```
Mod integer value 0 is strict : false

```

**程序 2:**

```
// Java program to illustrate isStrict()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier Integer value
        int mod = interfaceTest
                      .class
                      .getModifiers();

        // check Modifier is strict or not
        boolean result
            = Modifier.isStrict(mod);

        System.out.println("Mod integer value "
                           + mod + " is strict : "
                           + result);
    }

    strictfp interface interfaceTest {
        double method1();
        int method2();
    }
}
```

**Output:**

```
Mod integer value 1544 is strict : false

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # isStrict(int)](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#isStrict(int))