# 爪哇番石榴| Doubles.compare()方法与示例

> 原文:[https://www . geesforgeks . org/Java-guava-double-compare-method-with-examples/](https://www.geeksforgeeks.org/java-guava-doubles-compare-method-with-examples/)

**双打. compare()** 法番石榴的[双打类](https://www.geeksforgeeks.org/doubles-class-guava-java/)用于比较两个指定的*双*值。这些值作为参数传递，比较的结果是第一个值和第二个值的差值。因此它可以是正的、零的或负的。

**语法:**

```
public static int compare(double a, double b)

```

**参数:**该方法接受两个参数:

*   **a:** 是第一个要比较的双对象。
*   **b:** 这是第二个要比较的双对象。

**返回值:**这个方法返回一个 int 值。它返回:

*   如果“a”等于“b”，则为 0，
*   如果“a”大于“b”，则为正值，
*   如果“a”小于“b ”,则为负值

**异常:**该方法不抛出任何异常。

下面的程序说明了 Double.compare()方法:

**例 1:**

```
// Java code to show implementation of
// Guava's Doubles.compare() method

import com.google.common.primitives.Doubles;

class GFG {
    public static void main(String[] args)
    {
        double a = 4.0;
        double b = 4.0;

        // compare method in Double class
        int output = Doubles.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 4.0 and 4.0 : 0

```

**例 2:**

```
// Java code to show implementation of
// Guava's Doubles.compare() method

import com.google.common.primitives.Doubles;

class GFG {
    public static void main(String[] args)
    {
        double a = 5.6;
        double b = 4.2;

        // compare method in Double class
        int output = Doubles.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 5.6 and 4.2 : 1

```

**例 3:**

```
// Java code to show implementation of
// Guava's Doubles.compare() method

import com.google.common.primitives.Doubles;

class GFG {
    public static void main(String[] args)
    {
        double a = 3.6;
        double b = 7.4;

        // compare method in Double class
        int output = Doubles.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 3.6 and 7.4 : -1

```