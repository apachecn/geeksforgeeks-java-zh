# Java 中的布尔等于()方法，示例

> 原文:[https://www . geesforgeks . org/boolean-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/boolean-equals-method-in-java-with-examples/)

布尔类的 **equals()** 方法是 Java 的一个内置方法，用于检查两个布尔对象的相等性。

**语法:**

```java
BooleanObject.equals(Object ob)
```

**参数:**它以对象类型的参数 **ob** 作为输入，这是要比较的实例。

**返回类型:**返回类型为**布尔**。如果指定的对象“ob”与“BooleanObject”具有相同的值，则返回 true，否则返回 false。

下面是说明布尔类的 equals()方法的程序:

**程序 1:**

```java
// Java code to implement
// equals() method of Boolean class

class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // Boolean object
        Boolean a = new Boolean(true);

        // Boolean object
        Boolean b = new Boolean(true);

        // compare method
        System.out.println(a + " comparing with " + b
                           + " = " + a.equals(b));
    }
}
```

**Output:**

```java
true comparing with true = true

```

**程序 2:**

```java
// Java code to implement
// equals() method of Java class

class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // Boolean object
        Boolean a = new Boolean(true);

        // Boolean object
        Boolean b = new Boolean(false);

        // compare method
        System.out.println(a + " comparing with " + b
                           + " = " + a.equals(b));
    }
}
```

**Output:**

```java
true comparing with false = false

```

**程序 3:**

```java
// Java code to implement
// equals() method of Java class

class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // Boolean object
        Boolean a = new Boolean(false);

        // Boolean object
        Boolean b = new Boolean(true);

        // compare method
        System.out.println(a + " comparing with " + b
                           + " = " + a.equals(b));
    }
}
```

**Output:**

```java
false comparing with true = false

```