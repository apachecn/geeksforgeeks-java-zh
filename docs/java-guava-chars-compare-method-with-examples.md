# 爪哇番石榴| Chars.compare()方法与示例

> 原文:[https://www . geesforgeks . org/Java-guava-chars-compare-method-with-examples/](https://www.geeksforgeeks.org/java-guava-chars-compare-method-with-examples/)

**Chars.compare()** 番石榴的 [Chars 类](https://www.geeksforgeeks.org/chars-class-guava-java/)的方法用于比较两个指定的 *char* 值。这些值作为参数传递，比较的结果是第一个值和第二个值的差值。因此它可以是正的、零的或负的。

**语法:**

```java
public static int compare(char a, char b)

```

**参数:**该方法接受两个参数:

*   **a:** 是第一个要比较的 char 对象。
*   **b:** 是第二个要比较的 char 对象。

**返回类型:**这个方法返回一个 int 值。它返回:

*   如果“a”等于“b”，则为 0，
*   正值“a”大于“b”，
*   负值“a”小于“b”

**异常:**该方法没有任何异常。

**例 1:**

```java
// Java code to show implementation of
// Guava's Chars.compare() method
import com.google.common.primitives.Chars;

class GFG {
    public static void main(String[] args)
    {
        char a = 'c';
        char b = 'c';

        // compare method in Char class
        int output = Chars.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing c and c : 0

```

**例 2:**

```java
// Java code to show implementation of
// Guava's Chars.compare() method
import com.google.common.primitives.Chars;

class GFG {
    public static void main(String[] args)
    {
        char a = 'd';
        char b = 'D';

        // compare method in Char class
        int output = Chars.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing d and D : 32

```

**例 3:**

```java
// Java code to show implementation of
// Guava's Chars.compare() method
import com.google.common.primitives.Chars;

class GFG {
    public static void main(String[] args)
    {
        char a = 'E';
        char b = 'c';

        // compare method in Char class
        int output = Chars.compare(a, b);

        // printing the output
        System.out.println("Comparing " + a
                           + " and " + b + " : "
                           + output);
    }
}
```

**Output:**

```java
Comparing E and c : -30

```