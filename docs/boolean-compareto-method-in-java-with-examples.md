# Java 中的布尔 compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/boolean-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/boolean-compareto-method-in-java-with-examples/)

[布尔类](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)的 **compareTo()** 方法是 Java 中的一个内置方法，用于将给定的布尔实例与当前实例进行比较。

**语法:**

```
BooleanObject.compareTo(Boolean a)
```

**参数:**取布尔值 **a** 作为参数，与当前实例进行比较。

**返回类型:**功能的返回类型为 **int** 。它返回:

*   如果“a”等于“b”，则为 0，
*   如果“a”为假，“b”为真，则为负值，
*   如果“a”为真，“b”为假，则为正值。

下面是说明布尔类的 compareTo()方法的程序:

**程序 1:**

```
// Java code to implement
// compareTo() method of Boolean class

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
                           + " = " + a.compareTo(b));
    }
}
```

**Output:**

```
true comparing with true = 0

```

**程序 2:**

```
// Java code to implement
// compareTo() method of Java class

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
                           + " = " + a.compareTo(b));
    }
}
```

**Output:**

```
true comparing with false = 1

```

**程序 3:**

```
// Java code to implement
// compareTo() method of Java class

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
                           + " = " + a.compareTo(b));
    }
}
```

**Output:**

```
false comparing with true = -1

```