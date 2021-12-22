# Java 中的 Byte hashCode()方法，带示例

> 原文:[https://www . geesforgeks . org/byte-hashcode-method-in-Java-with-examples/](https://www.geeksforgeeks.org/byte-hashcode-method-in-java-with-examples/)

[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)的 **hashCode()** 方法是 Java 中的内置方法，用于返回 ByteObject 的哈希代码。

**注意:**hashCode()返回的值与 intValue()相同。

**语法**

```
ByteObject.hashCode()
```

**返回值:**它返回一个 **int** 值，代表指定字节对象的哈希码。

下面是 hashCode()方法在 Java 中的实现:

**例 1:**

```
// Java code to demonstrate
// Byte hashCode() method

class GFG {
    public static void main(String[] args)
    {

        String value = "74";

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(value);

        // hashCode of the Byte Object
        int output = b.hashCode();

        // printing the output
        System.out.println("HashCode of "
                           + b + " : " + output);
    }
}
```

**Output:**

```
HashCode of 74 : 74

```

**例 2:**

```
// Java code to demonstrate
// Byte hashCode() method

class GFG {
    public static void main(String[] args)
    {

        String value = "-17";

        // wrapping the byte value
        // in the wrapper class Byte
        Byte b = new Byte(value);

        // hashCode of the Byte Object
        int output = b.hashCode();

        // printing the output
        System.out.println("HashCode of "
                           + b + " : " + output);
    }
}
```

**Output:**

```
HashCode of -17 : -17

```