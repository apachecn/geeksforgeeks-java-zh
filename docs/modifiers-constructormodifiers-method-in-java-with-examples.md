# Java 中修饰符构造修饰符()方法，示例

> 原文:[https://www . geesforgeks . org/modifiers-constructor modifiers-method-in-Java-with-examples/](https://www.geeksforgeeks.org/modifiers-constructormodifiers-method-in-java-with-examples/)

**java.lang.reflect.Modifier 类**的 **constructorModifiers()** 方法用于获取整数值以及可应用于构造函数的源语言的修饰符。

**语法:**

```java
public static boolean constructorModifiers()

```

**参数:**此方法不接受任何内容。

**返回**:这个方法返回一个 **int 值**，将可以应用于构造函数的源语言修饰符组合在一起。

下面的程序说明了 constructorModifiers()方法:
**程序 1:**

```java
// Java program to illustrate
// constructorModifiers() method

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier using constructorModifiers()
        int result = Modifier.constructorModifiers();

        System.out.println("Constructor Modifiers: "
                           + Modifier.toString(result));
    }
}
```

**Output:**

```java
Constructor Modifiers: public protected private

```

**程序 2:**

```java
// Java program to illustrate
// constructorModifiers()

import java.lang.reflect.*;

public class GFG {

    public static void main(String[] args)
        throws NoSuchFieldException,
               SecurityException
    {

        // get Modifier
        // using constructorModifiers()
        int result
            = Modifier.constructorModifiers();

        System.out.println("Int Value: "
                           + result);
    }
}
```

**Output:**

```java
Int Value: 7

```

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/modifier . html # constructor modifiers()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Modifier.html#constructorModifiers--)