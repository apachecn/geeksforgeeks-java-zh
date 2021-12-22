# Java 中的双字节赋值()方法，示例

> 原文:[https://www . geesforgeks . org/double-byteevalue-method-in-Java-with-examples/](https://www.geeksforgeeks.org/double-bytevalue-method-in-java-with-examples/)

**java . lang . Double . Bytevalue()**是 Java 中的一个内置方法，它以字节形式返回该 Double 的值(通过转换为字节)。基本上，它用于将 Double 类型的原语转换缩小为字节值。

**语法:**

```
public byte byteValue()

```

**参数:**函数不接受任何参数。

**返回值:**该方法返回转换为类型*字节*的该对象表示的双精度值。

**例:**

```
Input : 12
Output : 12

Input : 1023
Output : -1

```

下面的程序说明了 java.lang.Double.byteValue()函数的使用:

**程序 1:**

```
// Program to illustrate the Double.byteValue() method
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Double value = 1023d;

        // Returns the value of Double as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);

        // Another example
        value = 12d;
        byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

**输出:**

```
Byte Value of num = -1
Byte Value of num = 12

```

**程序 2 :** 演示负数的字节值。

```
// Java code to illustrate java.lang.Double.byteValue() method
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Double value = -1023d;

        // Returns the value of Double as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);

        // Another example
        value = -12d;
        byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

**输出:**

```
Byte Value of num = 1
Byte Value of num = -12

```

**程序 3 :** 当一个十进制值在参数中传递时。

```
// Program to illustrate java.lang.Double.byteValue() method

import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Double value = 11.24;

        // Returns the value of Double as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);

        // Another example
        value = 6.0;
        byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

**输出:**

```
Byte Value of num = 11
Byte Value of num = 6

```

**程序 4 :** 当字符串值作为参数传递时。

```
// Code to illustrate Double.byteValue()
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Double value = "45";

        // Returns the value of Double as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

**编译错误:**

```
prog.java:9: error: incompatible types: String cannot be converted to Double
        Double value = "45";
                       ^
1 error
```

**参考**:[https://docs . Oracle . com/javase/8/docs/API/Java/lang/double . html # byteevalue–](https://docs.oracle.com/javase/8/docs/api/java/lang/Double.html#byteValue--)