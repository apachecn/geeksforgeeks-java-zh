# Java 中的 Byte doubleValue()方法，带示例

> 原文:[https://www . geesforgeks . org/byte-double-value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/byte-doublevalue-method-in-java-with-examples/)

[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)的 **doubleValue()** 方法是 Java 中的一个内置方法，用来将这个 Byte 对象的值作为 double 返回。

**语法**

```java
ByteObject.doubleValue()
```

**返回类型:**返回字节对象的值为**双**。

下面是 doubleValue()方法在 Java 中的实现:

**例 1:**

```java
// Java code to demonstrate
// Byte doubleValue() method

class GFG {
    public static void main(String[] args)
    {

        // byte value
        byte a = 17;

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(a);

        // doubleValue of the Byte Object
        double output = b.doubleValue();

        // printing the output
        System.out.println("Double value of "
                           + a + " is : " + output);
    }
}
```

**Output:**

```java
Double value of 17 is : 17.0

```

**例 2:**

```java
// Java code to demonstrate
// Byte doubleValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "17";

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(value);

        // doubleValue of the Byte Object
        double output = b.doubleValue();

        // printing the output
        System.out.println("Double value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Double value of 17 is : 17.0

```