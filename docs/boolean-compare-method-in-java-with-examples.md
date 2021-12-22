# Java 中的布尔比较()方法，示例

> 原文:[https://www . geesforgeks . org/boolean-compare-method-in-Java-with-examples/](https://www.geeksforgeeks.org/boolean-compare-method-in-java-with-examples/)

[布尔类](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)的 **compare()** 方法是 Java 中的内置方法，用于比较两个布尔值。这是一个静态方法，因此可以在不创建[布尔类](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)的任何对象的情况下调用，即直接使用类名。

**语法:**

```
Boolean.compare(boolean a, boolean b)
```

**参数:**取待比较参数中的两个布尔值 **a 和**。

**返回类型:**功能的返回类型为 **int** 。它回来了

*   如果“a”等于“b”，则为 0，
*   如果“a”为假，“b”为真，则为负值，
*   如果“a”为真，“b”为假，则为正值。

下面是说明布尔类的 compare()方法的程序:

**程序 1:**

```
// Java code to implement
// compare() method of Boolean class

class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // first value
        boolean a = true;

        // second value
        boolean b = true;

        // compare method
        System.out.println(a + " comparing with " + b
                           + " = " + Boolean.compare(a, b));
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
// compare() method of Java class

class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // first value
        boolean a = true;

        // second value
        boolean b = false;

        // compare method
        System.out.println(a + " comparing with " + b
                           + " = " + Boolean.compare(a, b));
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
// compare() method of Java class

class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // first value
        boolean a = false;

        // second value
        boolean b = true;

        // compare method
        System.out.println(a + " comparing with " + b
                           + " = " + Boolean.compare(a, b));
    }
}
```

**Output:**

```
false comparing with true = -1

```