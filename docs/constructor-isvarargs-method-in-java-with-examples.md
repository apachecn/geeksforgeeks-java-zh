# 构造函数是 Java 中的 isVarArgs()方法，带有示例

> 原文:[https://www . geesforgeks . org/constructor-isvarargs-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-isvarargs-method-in-java-with-examples/)

**Java . lang . reflect . Constructor 类**的 **isVarArgs()** 方法用于返回布尔值 true，如果该 Constructor 可以将可变数量的参数作为参数，否则该方法将返回 false。VarArgs 允许构造函数接受许多参数。当不知道在构造函数中要传递多少参数时，使用 VarArgs 是比 array 更好的传递参数的方法。

**语法:**

```java
public boolean isVarArgs()

```

**参数:**此方法不接受任何内容。

**返回**:当且仅当该可执行文件被声明接受可变数量的参数时，该方法返回真。

以下程序说明 isVarArgs()方法:
**程序 1:**

```java
// Java program to illustrate isVarArgs() method

import java.lang.annotation.Annotation;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = shape.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        // check isVargs or not
        boolean isVargs = cons[0].isVarArgs();

        // print result
        System.out.println("isVargs : " + isVargs);
    }

    public class shape {

        public shape(Object... objects)
        {
        }
    }
}
```

**Output:**

```java
isVargs : true

```

**程序 2:**

```java
// Java program to illustrate isVarArgs() method

import java.lang.annotation.Annotation;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        for (int i = 0; i < cons.length; i++) {
            // check isVargs or not
            boolean isVargs = cons[i].isVarArgs();

            // print result
            System.out.println(cons[i]);
            System.out.println("isVargs : " + isVargs);
        }
    }
}
```

**Output:**

> public java.lang.String(byte[]，int，int)
> isVargs:false
> public java.lang.String(byte[]，Java . nio . charset . charset)
> isVargs:false
> public Java . lang . string(byte[]，Java . lang . string)抛出 Java . io . unsupportdencodinegexception
> isVargs:false
> public Java . lang . string(byte[]，int，int，java.nio.charset.Charset)
> int)
> isVargs:false
> public Java . lang . string()
> isVargs:false
> public Java . lang . string(char[])
> isVargs:false
> public Java . lang . string(Java . lang . string)
> isVargs:false
> public Java . lang . string(char[]，int，int)
> isVargs:false
> public Java . lang . string(byte[]，int)

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # isVarArgs()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#isVarArgs())