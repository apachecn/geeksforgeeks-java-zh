# 爪哇番石榴|用例子比较短类的()方法

> 原文:[https://www . geeksforgeeks . org/Java-guava-用示例比较短类方法/](https://www.geeksforgeeks.org/java-guava-compare-method-of-short-class-with-examples/)

**短裤.比较()**法番石榴的[短裤类](https://www.geeksforgeeks.org/shorts-class-guava-java/)用于比较两个指定的*短*值。这些值作为参数传递，比较的结果是第一个值和第二个值的差值。因此它可以是正的、零的或负的。

**语法:**

```
public static int compare(short x, short y)
```

**参数:**该方法接受两个参数:

*   **x:** 是第一个要比较的 Short 对象。
*   **y:** 是要比较的 Short 对象。

**返回类型:**返回一个 **int** 值。它返回:

*   如果“x”等于“y”，则为 0，
*   正值“x”大于“y”，
*   负值“x”小于“y”

下面是 compare()方法在 Java 中的实现:
**示例 1:**

```
// Java code to show implementation of
// Guava's Shorts.compare() method
import com.google.common.primitives.Shorts;

class GFG {
    public static void main(String[] args)
    {

        short a = 4;

        short b = 4;

        // compare method in Short class
        int output = Shorts.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 4 and 4 : 0

```

**例 2:**

```
// Java code to show implementation of
// Guava's Shorts.compare() method
import com.google.common.primitives.Shorts;

class GFG {
    public static void main(String[] args)
    {

        short a = 4;

        short b = 2;

        // compare method in Short class
        int output = Shorts.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 4 and 2 : 2

```

**例 3:**

```
// Java code to show implementation of
// Guava's Shorts.compare() method
import com.google.common.primitives.Shorts;

class GFG {
    public static void main(String[] args)
    {

        short a = 2;

        short b = 4;

        // compare method in Short class
        int output = Shorts.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```
Comparing 2 and 4 : -2

```