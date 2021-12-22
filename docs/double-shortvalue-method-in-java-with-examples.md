# Java 中的 Double shortValue()方法，带示例

> 原文:[https://www . geesforgeks . org/double-short value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/double-shortvalue-method-in-java-with-examples/)

[Double](https://www.geeksforgeeks.org/java-lang-double-class-java/) 类的 **shortValue()** 方法是一个内置方法，用于在类型转换后将调用对象指定的值作为 short 返回。

**语法**:

```java
DoubleObject.shortValue()
```

**返回值:**它将 DoubleObject 的值返回为**简称**。

下面的程序说明了 Java 中的 shortValue()方法:
**程序 1:**

```java
// Java code to demonstrate
// Double shortValue() method

class GFG {
    public static void main(String[] args)
    {

        // Double value
        Double a = 17.47;

        // wrapping the Double value
        // in the wrapper class Double
        Double b = new Double(a);

        // shortValue of the Double Object
        short output = b.shortValue();

        // prshorting the output
        System.out.println("Short value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Short value of 17.47 is : 17

```

**程序 2:**

```java
// Java code to demonstrate
// Double shortValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "54.1";

        // wrapping the Double value
        // in the wrapper class Double
        Double b = new Double(value);

        // shortValue of the Double Object
        short output = b.shortValue();

        // prshorting the output
        System.out.println("Short value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```java
Short value of 54.1 is : 54

```