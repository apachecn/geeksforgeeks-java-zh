# Java 中的整数短值()方法

> 原文:[https://www . geesforgeks . org/integer-short value-method-in-Java/](https://www.geeksforgeeks.org/integer-shortvalue-method-in-java/)

Integer.shortValue()是 java.lang 的一个内置方法，它以 *short* 类型返回该整数的值。

**语法:**

```java
public short shortValue()

```

**参数**:该方法不取任何参数。

**返回值:**方法将该对象转换为 short 类型后，返回该对象表示的整数值。

下面的程序说明了 Integer.shortValue()方法:
**程序 1:** 为正整数。

```java
// Java program that demonstrates
// Integer.shortValue() method

import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        Integer sh_object = new Integer(763);

        // It will return the value of this Integer as a short type
        short sh_value = sh_object.shortValue();
        System.out.println(" The Value of sh_value = " + sh_value);
    }
}
```

**Output:**

```java
The Value of sh_value = 763

```

**程序 2:** 为负数。

```java
// Java program that demonstrates
// Integer.shortValue() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        Integer sh_object = new Integer(-43);

        // It will return the value of this Integer as a short type
        short sh_value = sh_object.shortValue();
        System.out.println(" The Value of sh_value = " + sh_value);
    }
}
```

**Output:**

```java
The Value of sh_value = -43

```

**程序 3:** 为十进制值和字符串。
**注意:**当十进制值和字符串作为参数传递时，它会返回一条错误消息。

```java
// java program that demonstrates
// Integer.shortValue() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        // passing a decimal value
        Integer sh_object = new Integer(27.51);

        short sh_value = sh_object.shortValue();
        System.out.println(" The Value of sh_value = " + sh_value);

        // passing a string
        Integer sh_object2 = new Integer("51");

        short sh_value2 = sh_object2.shortValue();
        System.out.println(" The Value of sh_value2 = " + sh_value2);
    }
}
```

**输出:**

```java
prog.java:10: error: no suitable constructor found for Integer(double)
    Integer sh_object = new Integer(27.51);
                        ^
    constructor Integer.Integer(int) is not applicable
      (argument mismatch; possible lossy conversion from double to int)
    constructor Integer.Integer(String) is not applicable
      (argument mismatch; double cannot be converted to String)
1 error

```