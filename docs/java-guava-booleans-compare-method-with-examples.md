# Java 番石榴| Booleans.compare()方法与示例

> 原文:[https://www . geesforgeks . org/Java-guava-booleans-compare-method-with-examples/](https://www.geeksforgeeks.org/java-guava-booleans-compare-method-with-examples/)

番石榴库中 **[布尔类](https://www.geeksforgeeks.org/booleans-class-guava-java/)** 的 **compare()** 方法用于比较两个指定的*布尔*值。这些值作为参数传递，比较的结果是第一个值和第二个值的差值。因此它可以是正的、零的或负的。

**语法:**

```
public static int compare(boolean a, boolean b)

```

**参数:**该方法接受两个参数:

*   **a:** 是第一个要比较的布尔对象。
*   **b:** 这是要比较的第二个布尔对象。

**返回值:**这个方法返回一个 int 值。它返回:

*   如果“a”等于“b”，则为 0，
*   如果“a”为真而“b”为假，则为正值，
*   如果“a”为假，“b”为真，则为负值

**异常:**该方法不抛出任何异常。

下面的程序说明了 Booleans.compare()方法:

**例 1:**

```
// Java code to show implementation of
// Guava's Booleans.compare() method

import com.google.common.primitives.Booleans;

class GFG {
    public static void main(String[] args)
    {
        boolean a = true;
        boolean b = true;

        // compare method in Booleans class
        int output = Booleans.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing true and true : 0

```

**例 2:**

```
// Java code to show implementation of
// Guava's Booleans.compare() method

import com.google.common.primitives.Booleans;

class GFG {
    public static void main(String[] args)
    {
        boolean a = true;
        boolean b = false;

        // compare method in Booleans class
        int output = Booleans.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing true and false : 1

```

**例 3:**

```
// Java code to show implementation of
// Guava's Booleans.compare() method

import com.google.common.primitives.Booleans;

class GFG {
    public static void main(String[] args)
    {

        boolean a = false;
        boolean b = true;

        // compare method in Booleans class
        int output = Booleans.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing false and true : -1

```