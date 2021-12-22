# Java 中的布尔 booleanValue()方法，带示例

> 原文:[https://www . geesforgeks . org/boolean-boolean value-method-in-Java-with-examples/](https://www.geeksforgeeks.org/boolean-booleanvalue-method-in-java-with-examples/)

[布尔类](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)的**布尔值()**方法是 java 中的一个内置方法，用于返回实例的原始布尔值，该值用于调用方法布尔值()。

**语法**

```
BooleanObject.booleanValue()
```

**返回值:**返回一个**原始布尔值。**

下面是说明 booleanValue()方法的示例:

**程序 1:**

```
class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // creating a Boolean object.
        Boolean b = new Boolean(true);

        // get primitive data type using booleanValue()
        boolean value = b.booleanValue();

        // Print the result
        System.out.println(value);
    }
}
```

**Output:**

```
true

```

**例 2:**

```
class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // creating a Boolean object.
        Boolean b = new Boolean(false);

        // get primitive data type using booleanValue()
        boolean value = b.booleanValue();

        // Print the result
        System.out.println(value);
    }
}
```

**Output:**

```
false

```