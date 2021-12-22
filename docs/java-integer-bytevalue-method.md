# Java Integer byteevalue()方法

> 原文:[https://www . geesforgeks . org/Java-integer-byteevalue-method/](https://www.geeksforgeeks.org/java-integer-bytevalue-method/)

java.lang 包的 Integer 类的 **byteValue()** 方法，在一个收缩原语转换后，将给定的 Integer 转换为一个字节，然后返回。

**语法:**

```java
public byte byteValue()

Return :
This method returns the numeric value represented by this object after
 conversion to byte type.

```

**示例:**展示**Java . lang . integer . Bytevalue()**方法的工作。

```java
// Java program to demonstrate working
// of java.lang.Integer.byteValue() method
import java.lang.Integer;

class Gfg {
    // driver code
    public static void main(String args[])
    {
        Integer a = new Integer(34);

        // Convert Integer number to byte value
        byte b = a.byteValue();

        System.out.println(b);
    }
}
```

**输出:**

```java
34

```