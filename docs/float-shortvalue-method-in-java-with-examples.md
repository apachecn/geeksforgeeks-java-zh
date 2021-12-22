# Java 中的 Float shortValue()方法，带示例

> 原文:[https://www . geesforgeks . org/float-short value-in-Java-method-with-examples/](https://www.geeksforgeeks.org/float-shortvalue-method-in-java-with-examples/)

**[Float 类](https://www.geeksforgeeks.org/java-lang-float-class-in-java/)** 中的 **shortValue()** 方法是 Java 中的一个内置方法，它在类型转换后将对象调用为 short 来返回指定的值。

**语法**:

```
public short shortValue()
```

**返回值:**返回**简称**的浮点值。

下面的程序说明了 Java 中的 **shortValue()** 方法:
T3】程序 1:

```
// Java code to demonstrate
// Float shortValue() method

class GFG {
    public static void main(String[] args)
    {

        // Float value
        Float a = 17.47f;

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(a);

        // shortValue of the Float Object
        short output = b.shortValue();

        // prshorting the output
        System.out.println("Short value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Short value of 17.47 is : 17

```

**程序 2:**

```
// Java code to demonstrate
// Float shortValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "54.1f";

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(value);

        // shortValue of the Float Object
        short output = b.shortValue();

        // prshorting the output
        System.out.println("Short value of "
                           + b + " is : " + output);
    }
}
```

**Output:**

```
Short value of 54.1 is : 54

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # short value()](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#shortValue())