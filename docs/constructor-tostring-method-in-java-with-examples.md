# Java 中的构造函数 toString()方法，示例

> 原文:[https://www . geesforgeks . org/constructor-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/constructor-tostring-method-in-java-with-examples/)

**Java . lang . reflect . Constructor 类**的 **toString()** 方法用于返回该构造函数的字符串表示。此字符串是此构造函数所有属性的集合。为了创建这个字符串方法，用构造函数的声明类的名称添加构造函数的访问修饰符，然后添加括号，并一起添加构造函数的形式参数类型的逗号分隔列表。

**语法:**

```java
public String toString()

```

**参数:**此方法不接受任何内容。

**返回**:此方法返回描述此构造函数的**字符串**。

下面的程序说明了 toString()方法:
**程序 1:**

```java
// Java program to illustrate toString() method

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
        String str = cons[0].toString();

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
Constructor : public GFG$shape(GFG, java.lang.Object[])

```

**程序 2:**

```java
// Java program to illustrate toString() method

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

            String str = cons[i].toString();

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

**参考文献:**[https://docs . Oracle . com/javase/10/docs/API/Java/lang/reflect/constructor . html # toString()](https://docs.oracle.com/javase/10/docs/api/java/lang/reflect/Constructor.html#toString())