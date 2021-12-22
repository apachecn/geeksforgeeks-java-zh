# Java 中的双浮点值()，示例

> 原文:[https://www . geeksforgeeks . org/double-float value-in-Java-with-examples/](https://www.geeksforgeeks.org/double-floatvalue-in-java-with-examples/)

[Double](https://www.geeksforgeeks.org/java-lang-double-class-java/) 类的 **floatValue()** 方法是一个内置方法，用于在类型转换后将调用对象指定的值作为 float 返回。

**语法**

```java
DoubleObject.floatValue()

```

**参数:**不取参数。

**返回类型:**它返回一个**浮点**值，即 DoubleObject 的类型铸造值。

下面是上述方法的实现。

**代码 1 :**

```java
// Java Code to implement 
// floatValue() method of Double class
class GFG {

    public static void main(String[] args)
    {
        // creating a Double object
        Double d = new Double(23);

        // floatValue() method of Double class
        // typecast the value
        float output = d.floatValue();

        // printing the output
        System.out.println(output);
    }
}
```

**输出**

```java
23.0

```

**代码 2 :**

```java
// Java Code to implement 
// floatValue() method 
// of Double class
class GFG {

    public static void main(String[] args)
    {
        // creating a Double object
        Double d = new Double(-1023.15);

        // floatValue() method of Double class
        // typecast the value
        float output = d.floatValue();

        // printing the output
        System.out.println(output);
    }
}
```

**输出**

```java
-1023.15

```