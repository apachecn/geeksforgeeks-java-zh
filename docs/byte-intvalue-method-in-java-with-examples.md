# Java 中的 Byte intValue()方法，带示例

> 原文:[https://www . geesforgeks . org/byte-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/byte-intvalue-method-in-java-with-examples/)

[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)的 **intValue()** 方法是 Java 中的内置方法，用于将这个 Byte 对象的值作为 int 返回。

**语法**

```java
ByteObject.intValue()
```

**返回值:**返回字节对象的值为 **int** 。

下面是 intValue()方法在 Java 中的实现:

**例 1:**

```java
// Java code to demonstrate
// Byte intValue() method

class GFG {
    public static void main(String[] args)
    {

        // byte value
        byte a = 17;

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(a);

        // intValue of the Byte Object
        int output = b.intValue();

        // printing the output
        System.out.println("Integer value of "
                           + a + " is : " + output);
    }
}
```

**Output:**

```java
Integer value of 17 is : 17

```

**例 2:**

```java
// Java code to demonstrate
// Byte intValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "17";

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(value);

        // intValue of the Byte Object
        int output = b.intValue();

        // printing the output
        System.out.println("Integer value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Integer value of 17 is : 17

```