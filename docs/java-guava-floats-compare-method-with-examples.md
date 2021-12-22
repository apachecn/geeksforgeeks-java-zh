# Java 番石榴| Floats.compare()方法与示例

> 原文:[https://www . geesforgeks . org/Java-guava-floats-compare-method-with-examples/](https://www.geeksforgeeks.org/java-guava-floats-compare-method-with-examples/)

**Floats . compare()[Floats 类](https://www.geeksforgeeks.org/floats-class-guava-java/)的**方法用于比较两个指定的*Floats*值。这些值作为参数传递，比较的结果是第一个值和第二个值的差值。因此它可以是正的、零的或负的。

**语法:**

```java
public static int compare(float a, float b)

```

**参数:**该方法接受两个参数:

*   **a:** 是第一个要比较的浮动对象。
*   **b:** 是第二个要比较的浮动对象。

**返回类型:**这个方法返回一个 int 值。它返回:

*   如果“a”等于“b”，则为 0，
*   正值“a”大于“b”，
*   负值“a”小于“b”

**异常:**该方法不抛出任何异常。

**例 1:**

```java
// Java code to show implementation of
// Guava's Floats.compare() method
import com.google.common.primitives.Floats;

class GFG {
    public static void main(String[] args)
    {
        float a = 4f;
        float b = 4f;

        // compare method in Float class
        int output = Floats.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 4.0 and 4.0 : 0

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Floats.compare() method
import com.google.common.primitives.Floats;

class GFG {
    public static void main(String[] args)
    {
        float a = 4.2f;
        float b = 3.1f;

        // compare method in Float class
        int output = Floats.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 4.2 and 3.1 : 1

```

**例 3:**

```java
// Java code to show implementation of
// Guava's Floats.compare() method
import com.google.common.primitives.Floats;

class GFG {
    public static void main(String[] args)
    {
        float a = 2.5f;
        float b = 4f;

        // compare method in Float class
        int output = Floats.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing 2.5 and 4.0 : -1

```