# Java 中的布尔 parseBoolean()方法，带示例

> 原文:[https://www . geesforgeks . org/boolean-parseboolean-method-in-Java-with-examples/](https://www.geeksforgeeks.org/boolean-parseboolean-method-in-java-with-examples/)

[布尔类](https://www.geeksforgeeks.org/java-lang-boolean-class-java/)的 **parseBoolean()** 方法是类**的内置静态方法，用于将给定字符串转换为其布尔值。**

**语法:**

```
Boolean.parseBoolean(String value)
```

**参数:**取类型字符串的一个参数**值**，该值包含要转换为布尔值的值。

**返回值:**返回一个原始布尔值。如果给定值等于“真”忽略案例，则返回**真**。否则返回**假**。

下面是 java 代码来说明 parseBoolean()方法:

**例 1:**

```
class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // string value
        String value = "TrUe";

        // parseBoolean using parse Boolean() method
        boolean result = Boolean.parseBoolean(value);

        // printing the result
        System.out.println(result);
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

        // string value
        String value = "true";

        // parseBoolean using parse Boolean() method
        boolean result = Boolean.parseBoolean(value);

        // printing the result
        System.out.println(result);
    }
}
```

**Output:**

```
true

```

**例 3:**

```
class GeeksforGeeks {

    // Driver method
    public static void main(String[] args)
    {

        // string value
        String value = "gfg";

        // parseBoolean using parse Boolean() method
        boolean result = Boolean.parseBoolean(value);

        // printing the result
        System.out.println(result);
    }
}
```

**Output:**

```
false

```