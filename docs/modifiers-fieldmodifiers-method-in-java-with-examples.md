# 修饰符 Java 中的 fieldModifiers()方法，示例

> 原文:[https://www . geesforgeks . org/modifiers-field modifiers-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifiers-fieldmodifiers-method-in-java-with-examples/)

**java.lang.reflect.Modifier 类**的 **fieldModifiers()** 方法用于获取整数值以及可应用于字段的源语言的修饰符。

**语法:**

```java
public static boolean fieldModifiers()

```

**参数:**此方法不接受任何内容。

**返回**:该方法返回一个**整数值**，将可应用于字段的源语言修饰符组合在一起。
。

下面的程序说明了 fieldModifiers()方法:
**程序 1:**

```java
// Java program to illustrate
// fieldModifiers() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier using fieldModifiers()
        int result = Modifier.fieldModifiers();

        System.out.println(
            "Field Modifiers: "
            + Modifier.toString(result));
    }
}
```

**Output:**

```java
Field Modifiers: public protected private static final transient volatile

```

**程序 2:**

```java
// Java program to illustrate fieldModifiers()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier using fieldModifiers()
        int result = Modifier.fieldModifiers();

        System.out.println(
            "Int Value: "
            + result);
    }
}
```

**Output:**

```java
Int Value: 223

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # field modifiers()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#fieldModifiers--)