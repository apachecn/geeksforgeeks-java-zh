# Java 中的 Double doubleValue()方法，带示例

> 原文:[https://www . geesforgeks . org/double-double-value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/double-doublevalue-method-in-java-with-examples/)

[Double](https://www.geeksforgeeks.org/java-lang-double-class-java/) 类的 **doubleValue()** 方法是一个内置方法，用于在类型转换后将调用对象指定的值作为 Double 返回。

**语法**:

```
DoubleObject.doubleValue()
```

**返回值:**返回双对象的值为**双**。

下面的程序说明了 Java 中的 doubleValue()方法:

**程序 1:**

```
// Java code to demonstrate
// Double doubleValue() method

class GFG {
    public static void main(String[] args)
    {

        // Double value
        Double a = 17.47;

        // wrapping the Double value
        // in the wrapper class Double
        Double b = new Double(a);

        // doubleValue of the Double Object
        double output = b.doubleValue();

        // prdoubleing the output
        System.out.println("Double value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Double value of 17.47 is : 17.47

```

**程序 2:**

```
// Java code to demonstrate
// Double doubleValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "54.1";

        // wrapping the Double value
        // in the wrapper class Double
        Double b = new Double(value);

        // doubleValue of the Double Object
        double output = b.doubleValue();

        // prdoubleing the output
        System.out.println("Double value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Double value of 54.1 is : 54.1

```