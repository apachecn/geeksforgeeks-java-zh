# Java 中的模或余数运算符

> 原文:[https://www . geesforgeks . org/模或余数运算符 in-java/](https://www.geeksforgeeks.org/modulo-or-remainder-operator-in-java/)

模或余数运算符在除法后返回两个数的余数。如果你有两个数字，比如 A 和 B，A 是被除数，B 是除数，A 模 B 是 A 和 B 除的余数。模运算符是算术运算符，用%表示。

**语法:**

```
A % B
Where A is the dividend and B is divisor
```

**示例:**

> **输入** : a = 15，b = 6
> // 15%6 表示当我们用 15(分子)除以 6(分母)时，我们得到余数 3/
> /**输出** : 3
> **输入** : a = 16，b = 4
> **输出:** 0

**进场:**

1.  从用户那里获取被除数和除数。
2.  创建一个整数变量，并用 A % B 表达式赋值。
3.  打印该变量。

下面是上述方法的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Implementation of Modulo or Remainder Operator in Java
import java.io.*;
import java.util.*;

class GFG {
    public static void main(String[] args)
    {
        // Dividend
        int a = 15;

        // Divisor
        int b = 8;

        // Mod
        int k = a % b;
        System.out.println(k);
    }
}
```

**Output**

```
7
```

**时间复杂度:**

像其他算术运算一样，模函数通常需要恒定的时间。