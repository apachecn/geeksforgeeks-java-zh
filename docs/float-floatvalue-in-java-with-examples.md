# Java 中的 Float floatValue()示例

> 原文:[https://www . geesforgeks . org/float-float value-in-Java-with-examples/](https://www.geeksforgeeks.org/float-floatvalue-in-java-with-examples/)

[**Float 类**](https://www.geeksforgeeks.org/java-lang-float-class-in-java/) 中的 **floatValue()** 方法是 java 中的内置函数，在类型转换后将调用对象指定的值作为 Float 返回。

**语法**:

```java
public float floatValue()

```

**返回值:**将浮点对象的值作为**浮点**返回。

下面的程序用 Java 说明了**浮点值()**方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate
// Float floatValue() method

class GFG {
    public static void main(String[] args)
    {

        // Float value
        Float a = 17.47f;

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(a);

        // floatValue of the Float Object
        float output = b.floatValue();

        // prfloating the output
        System.out.println("Float value of "
                           + b + " is : " + output);
    }
}
```

**Output:** 

```java
Float value of 17.47 is : 17.47

```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code to demonstrate
// Float floatValue() method

class GFG {
    public static void main(String[] args)
    {

        String value = "54.1";

        // wrapping the Float value
        // in the wrapper class Float
        Float b = new Float(value);

        // floatValue of the Float Object
        float output = b.floatValue();

        // prfloating the output
        System.out.println("Float value of "
                           + b + " is : " + output);
    }
}
```

**Output:** 

```java
Float value of 54.1 is : 54.1

```

**参考:**T2【https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # float value()T4】