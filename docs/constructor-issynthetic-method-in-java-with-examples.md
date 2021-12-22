# 构造函数是 Java 中的 synintellic()方法，带有示例

> 原文:[https://www . geeksforgeeks . org/constructor-is synintellic-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-issynthetic-method-in-java-with-examples/)

如果此构造函数对象是一个合成构造函数，则使用**Java . lang . reflect . constructor 类**的**issynamic()**方法返回布尔值 true，否则该方法返回 false，表示此构造函数不是合成构造函数。正如我们所知，合成构造是由 Java 编译器出于内部目的而创建的类、字段和方法。就构造函数而言，合成构造函数是由 java 编译器为内部使用而创建的构造函数。这种方法有助于识别那些结构。

**语法:**

```java
public boolean isSynthetic()

```

**参数:**此方法不接受任何内容。

**返回**:当且仅当该可执行文件是由 Java 语言规范定义的合成构造时，该方法返回真。

下面的程序说明了 isSynthetic()方法:
**程序 1:**

```java
// Java program to illustrate isSynthetic() method

import java.lang.reflect.Constructor;

public class GFG {

    public static void main(String[] args)
    {
        // create a class object
        Class classObj = shape.class;

        // get Constructor object
        // array from class object
        Constructor[] cons = classObj.getConstructors();

        // check isSynthetic or not
        boolean answer = cons[0].isSynthetic();

        // print result
        System.out.println("isSynthetic : " + answer);
    }

    @CustomAnnotation(createValues = "GFG")
    public class shape {

        @CustomAnnotation(createValues = "GFG")
        public shape()
        {
        }
    }

    // create a custom annotation
    public @interface CustomAnnotation {
        public String createValues();
    }
    }
```

**Output:**

```java
isSynthetic : false

```

**程序 2:**

```java
// Java program to illustrate isSynthetic() method

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

            System.out.println("Constructor: "
                               + cons[i]);

            // get array of isSynthetic
            boolean answer = cons[0].isSynthetic();

            // print result
            System.out.println("isSynthetic : " + answer);
        }
    }
}
```

**Output:**

> 构造函数:public java.lang.String(byte[]，int，int)
> issynamic:false
> 构造函数:public java.lang.String(byte[]，Java . nio . charset . charset)
> issynamic:false
> 构造函数:public java.lang.String(byte[]，java.lang.String)抛出 Java . io . unsupportdencodinegexception
> issynamic:false
> 构造函数:public java.lang.String(byte[]，int，int，Java . nio . char。 int，int)
> issynamic:false
> 构造函数:public java.lang . string()
> issynamic:false
> 构造函数:public java.lang.String(char[])
> issynamic:false
> 构造函数:public Java . lang . string(Java . lang . string)
> issynamic:false
> 构造函数:public Java . lang . string(char[]，int，int)
> issynamic:false
> 构造函数:public Java . lang

**参考文献:**T2