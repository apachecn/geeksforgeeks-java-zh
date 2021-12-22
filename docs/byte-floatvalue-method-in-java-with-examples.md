# Java 中的字节浮点值()方法，带示例

> 原文:[https://www . geesforgeks . org/byte-float value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/byte-floatvalue-method-in-java-with-examples/)

[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)的 **floatValue()** 方法是 Java 中的一个内置方法，用于将这个 Byte 对象的值作为 float 返回。

**语法**

```
ByteObject.floatValue()
```

**返回值:**将字节对象的值作为**浮点**返回。

下面是 floatValue()方法在 Java 中的实现:

**例 1:**

```
// Java code to demonstrate
// Byte floatValue() method

class GFG {
    public static void main(String[] args)
    {

        // byte value
        byte a = 17;

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(a);

        // floatValue of the Byte Object
        float output = b.floatValue();

        // printing the output
        System.out.println("Float value of "
                           + a + " is : " + output);
    }
}
```

**Output:**

```
Float value of 17 is : 17.0

```

**例 2:**

```
// Java code to demonstrate
// Byte floatValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "17";

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(value);

        // floatValue of the Byte Object
        float output = b.floatValue();

        // printing the output
        System.out.println("Float value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Float value of 17 is : 17.0

```