# 爪哇郎。Java 中的 Long.byteValue()方法，示例

> 原文:[https://www . geesforgeks . org/Java-lang-long-byteevalue-method-Java-examples/](https://www.geeksforgeeks.org/java-lang-long-bytevalue-method-java-examples/)

**java . lang . Long . byteevalue()**是 Java 中的一个内置函数，它将这个 Long 的值作为一个字节返回。

**语法:**

```java
public byte byteValue()
Parameters: The function does not accept any parameter.
Return :
This method returns the numeric value 
represented by this object after conversion to byte type.

```

示例:

```java
Input : 12
Output : 12

Input : 1023
Output : -1

```

下面的程序说明了 java.lang.Long.byteValue()函数:

**程序 1 :**

```java
// Java program that demonstrates the use of
// Long.byteValue() function

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Long value = 1023l;

        // returns the value of Long as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);

        // 2nd example
        value = 12l;
        byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

输出:

```java
Byte Value of num = -1
Byte Value of num = 12

```

**程序 2 :** 演示负数的字节值

```java
// Java program that demonstrates the use of
// Long.byteValue() function
// negative number

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Long value = -1023l;

        // returns the value of Long as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);

        // 2nd example
        value = -12l;
        byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

输出:

```java
Byte Value of num = 1
Byte Value of num = -12

```

**程序 3 :** 当一个十进制值在参数中传递时。

```java
// Java program that demonstrates the use of
// Long.byteValue() function
// decimal number

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Long value = 11.24;

        // returns the value of Long as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

输出:

```java
prog.java:13: error: incompatible types: double cannot be converted to Long
        Long value = 11.24;

```

**程序 4 :** 当一个字符串值在参数中传递时。

```java
// Java program that demonstrates the use of
// Long.byteValue() function
// string number

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        Long value = "24";

        // returns the value of Long as a byte
        byte byteValue = value.byteValue();
        System.out.println("Byte Value of num = " + byteValue);
    }
}
```

输出:

```java
prog.java:13: error: incompatible types: String cannot be converted to Long
        Long value = "24";

```