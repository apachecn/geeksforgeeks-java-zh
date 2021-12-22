# Java 中的字节比较()方法，示例

> 原文:[https://www . geesforgeks . org/byte-compare-method-in-Java-with-examples/](https://www.geeksforgeeks.org/byte-compare-method-in-java-with-examples/)

[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)的 **compare()** 方法是 Java 中的内置方法，用于比较两个字节值。

**语法**

```java
Byte.compare(byte a, byte b)
```

**参数:**在待比较的参数中，取两个字节值**‘a’和‘b’**作为输入。

**返回值:**返回一个 **int** 值。它返回:

*   0 如果“a”等于“b ”,
*   正值“a”大于“b”，
*   负值“b”大于“a”

下面是 compare()方法在 Java 中的实现:

**例 1:**

```java
// Java code to demonstrate
// Byte compare() method

class GFG {
    public static void main(String[] args)
    {

        // byte value 'a'
        byte a = 20;

        // byte value 'b'
        byte b = 20;

        // compare method of Byte class
        int output = Byte.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 20 and 20 : 0

```

**例 2:**

```java
// Java code to demonstrate
// Byte compare() method

class GFG {
    public static void main(String[] args)
    {

        // byte value 'a'
        byte a = 20;

        // byte value 'b'
        byte b = 10;

        // compare method of Byte class
        int output = Byte.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 20 and 10 : 10

```

**例 3:**

```java
// Java code to demonstrate
// Byte compare() method

class GFG {
    public static void main(String[] args)
    {

        // byte value 'a'
        byte a = 10;

        // byte value 'b'
        byte b = 20;

        // compare method of Byte class
        int output = Byte.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 10 and 20 : -10

```