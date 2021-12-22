# Java 中的 Byte longValue()方法，带示例

> 原文:[https://www . geesforgeks . org/byte-long value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/byte-longvalue-method-in-java-with-examples/)

[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)的 **longValue()** 方法是 Java 中的一个内置方法，用来将这个 Byte 对象的值返回为 long。

**语法**

```java
ByteObject.longValue()
```

**返回值:**返回字节对象的值为**长**。

下面是 longValue()方法在 Java 中的实现:

**例 1:**

```java
// Java code to demonstrate
// Byte longValue() method

class GFG {
    public static void main(String[] args)
    {

        // byte value
        byte a = 17;

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(a);

        // longValue of the Byte Object
        long output = b.longValue();

        // printing the output
        System.out.println("Long value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Long value of 17 is : 17

```

**例 2:**

```java
// Java code to demonstrate
// Byte longValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "17";

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(value);

        // longValue of the Byte Object
        long output = b.longValue();

        // printing the output
        System.out.println("Long value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Long value of 17 is : 17

```