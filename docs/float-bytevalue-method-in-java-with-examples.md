# Java 中的 Float byteValue()方法，示例

> 原文:[https://www . geesforgeks . org/float-byteevalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/float-bytevalue-method-in-java-with-examples/)

**[java . lang . Float . Bytevalue()](https://www.geeksforgeeks.org/java-lang-float-class-in-java/)**是 Java 中的一个内置方法，它将这个 Float 的值作为一个字节返回(通过转换为一个字节)。基本上，它用于将浮点类型的原语转换缩小为字节值。

**语法:**

```java
public byte byteValue()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回转换为类型*字节*的该对象表示的浮点值。

**例:**

```java
Input : 12
Output : 12

Input : 1023
Output : -1

```

下面的程序说明了 java.lang.Float.byteValue()函数:

**程序 1:**

```java
// Program to illustrate the Float.byteValue() method
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Float value = 1023f;

        // Returns the value of Float as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);

        // Another example
        value = 12f;
        byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

**输出:**

```java
Byte Value of num = -1
Byte Value of num = 12

```

**程序 2 :** 演示负数的字节值。

```java
// Java code to illustrate java.lang.Float.byteValue() method
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Float value = -1023f;

        // Returns the value of Float as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);

        // Another example
        value = -12f;
        byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

**输出:**

```java
Byte Value of num = 1
Byte Value of num = -12

```

**程序 3 :** 当一个十进制值在参数中传递时。

```java
// Program to illustrate java.lang.Float.byteValue() method

import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Float value = 11.24f;

        // Returns the value of Float as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);

        // Another example
        value = 6.0f;
        byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

**输出:**

```java
Byte Value of num = 11
Byte Value of num = 6

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # byteevalue()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#byteValue())