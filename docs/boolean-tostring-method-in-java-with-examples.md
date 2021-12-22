# Java 中的布尔 toString()方法，带示例

> 原文:[https://www . geesforgeks . org/boolean-tostring-method-in-Java-with-examples/](https://www.geeksforgeeks.org/boolean-tostring-method-in-java-with-examples/)

[布尔类](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)的 **toString()** 方法是一个以字符串格式返回布尔值的内置方法。

在 Java 的布尔类中有两个 toString()方法的重载:

### 公共静态字符串(布尔值)

**语法**

```java
Boolean.toString(boolean value)
```

**参数**:取一个布尔**值**作为输入，转换为字符串。

**返回类型:**返回值是表示布尔值的**字符串**。

下面是说明 toString()方法的程序:

**程序 1:**

```java
// java code to demonstrate
// Boolean toString() method

class GFG {
    public static void main(String[] args)
    {

        // boolean type value
        boolean value = true;

        // static toString() method of Boolean class
        String output = Boolean.toString(value);

        // printing the value
        System.out.println(output);
    }
}
```

**Output:**

```java
true

```

**程序 2:**

```java
// java code to demonstrate
// Boolean toString() method

class GFG {
    public static void main(String[] args)
    {

        // boolean type value
        boolean value = false;

        // static toString() method of Boolean class
        String output = Boolean.toString(value);

        // printing the value
        System.out.println(output);
    }
}
```

**Output:**

```java
false

```

### 公共字符串 toString()

**语法**

```java
BooleanObject.toString()
```

**返回类型:**返回值是调用该方法的布尔实例的字符串表示形式。

以下是说明上述方法的程序:

**程序 1:**

```java
// java code to demonstrate
// Boolean toString() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Boolean object
        Boolean b = new Boolean(true);

        // toString method of Boolean class
        String output = b.toString();

        // printing the output
        System.out.println(output);
    }
}
```

**Output:**

```java
true

```

**程序 2:**

```java
// Java code to demonstrate
// Boolean toString() method

class GFG {
    public static void main(String[] args)
    {

        // creating a Boolean object
        Boolean b = new Boolean(false);

        // toString method of Boolean class
        String output = b.toString();

        // printing the output
        System.out.println(output);
    }
}
```

**Output:**

```java
false

```