# Java 中的 Byte equals()方法，示例

> 原文:[https://www . geesforgeks . org/byte-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/byte-equals-method-in-java-with-examples/)

[字节类](https://www.geeksforgeeks.org/java-lang-byte-class-java/)的 **equals()** 方法是 Java 中的一个内置方法，用于比较给定对象的等式和调用 **equals()** 方法的字节实例。

**语法**

```
ByteObject.equals(Object a)
```

**参数:**它将一个对象类型对象 **a** 作为输入，与调用**等于**方法的字节对象的实例进行比较。

**返回值:**返回一个**布尔**值。如果“a”的值等于 ByteObject 的值，则返回 true。

下面是 equals()方法在 Java 中的实现:

**例 1:**

```
// Java code to demonstrate
// Byte equals() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Byte object
        Byte a = new Byte("20");

        // creating a Byte object
        Byte b = new Byte("20");

        // equals method in Byte class
        boolean output = a.equals(b);

        // Printing the output
        System.out.println("Does " + a + " equals "
                           + b + " : " + output);
    }
}
```

**Output:**

```
Does 20 equals 20 : true

```

**例 2:**

```
// Java code to demonstrate
// Byte equals() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Byte object
        Byte a = new Byte("2");

        // creating a Byte object
        Byte b = new Byte("20");

        // equals method in Byte class
        boolean output = a.equals(b);

        // Printing the output
        System.out.println("Does " + a + " equals "
                           + b + " : " + output);
    }
}
```

**Output:**

```
Does 2 equals 20 : false

```