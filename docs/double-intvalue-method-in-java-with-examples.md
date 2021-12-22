# Java 中的 Double intValue()方法，带示例

> 原文:[https://www . geesforgeks . org/double-int value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/double-intvalue-method-in-java-with-examples/)

[Double](https://www.geeksforgeeks.org/java-lang-double-class-java/) 类的 **intValue()** 方法是一个内置方法，用于在类型转换后将调用对象指定的值作为 int 返回。

**语法**:

```
DoubleObject.intValue()
```

**返回值:**返回双对象的值为 **int** 。

下面的程序用 Java 说明了 intValue()方法:

**程序 1:**

```
// Java code to demonstrate
// Double intValue() method

class GFG {
    public static void main(String[] args)
    {

        // Double value
        Double a = 17.47;

        // wrapping the Double value
        // in the wrapper class Double
        Double b = new Double(a);

        // intValue of the Double Object
        int output = b.intValue();

        // printing the output
        System.out.println("Int value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Int value of 17.47 is : 17

```

**程序 2:**

```
// Java code to demonstrate
// Double intValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "54.1";

        // wrapping the Double value
        // in the wrapper class Double
        Double b = new Double(value);

        // intValue of the Double Object
        int output = b.intValue();

        // printing the output
        System.out.println("Int value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Int value of 54.1 is : 54

```