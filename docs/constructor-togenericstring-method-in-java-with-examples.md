# Java 中的构造函数 toGenericString()方法，示例

> 原文:[https://www . geeksforgeeks . org/constructor-togenericstring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-togenericstring-method-in-java-with-examples/)

**Java . lang . reflect . constructor 类**的**togetnericstring()**方法用于返回获取此构造函数的泛型形式，即表示此构造函数的详细信息(包括类型参数)的字符串。

**语法:**

```java
public String toGenericString()

```

**参数:**此方法不接受任何内容。

**Return** :这个方法返回这个构造函数的一个泛型形式，作为一个字符串，描述这个构造函数和类型参数。

下面的程序说明了 toGenericString()方法:
**程序 1:**

```java
// Java program to illustrate
// toGenericString() method

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

        // check get string representation
        String str = cons[0].toGenericString();

        // print result
        System.out.println("Constructor : " + str);
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
Constructor : public GFG$shape(GFG, java.lang.Object...)

```

**程序 2:**

```java
// Java program to illustrate
// toGenericString() method

import java.lang.annotation.Annotation;
import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = String.class;

        // get Constructor object
        // array from class object
        Constructor[] cons
            = classObj.getConstructors();

        for (int i = 0; i < cons.length; i++) {

            String str = cons[i].toGenericString();

            // print result
            System.out.println(str);
        }
    }
}
```

**Output:**

> public java.lang.String(byte[]，int，int)
> public java.lang.String(byte[]，Java . nio . charset . charset)
> public java.lang.String(byte[]，Java . lang . string)抛出 java.io . unsupportdencodinegexception
> public Java . lang . string(byte[]，int，int，Java . lang . string)抛出 Java . io。

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # toGenericString()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#toGenericString())