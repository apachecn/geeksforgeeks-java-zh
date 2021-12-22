# Java 中的 MathContext getPrecision()方法

> 原文:[https://www . geesforgeks . org/math context-get precision-method-in-Java/](https://www.geeksforgeeks.org/mathcontext-getprecision-method-in-java/)

**java . math . MathContext . getprecision()**是 Java 中的内置函数，返回 math context 对象的精度设置。该值总是非负的。

**语法:**

```
public int getPrecision()
```

**参数:**该方法不取任何参数。

**返回值:**这个方法返回一个 **int** ，它是 MathContext 对象的精度设置值。

**示例:**

```
Input : m1 = new MathContext(7); 
Output : 7

Input : m1 = new MathContext(2, RoundingMode.HALF_UP);
Output : 2

```

以下程序说明了 getPrecision()函数的使用:
**程序 1 :**

```
// Java program to demonstrate getPrecision() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a MathContext object m1
        MathContext m1;

        // Assign context settings to m1
        m1 = new MathContext(2, RoundingMode.HALF_UP);

        // Displaying the result
        System.out.println(m1.getPrecision());
    }
}
```

**Output:**

```
2

```

**程序 2 :**

```
// Java program to demonstrate getPrecision() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a MathContext object
        MathContext m1;

        // Assign context settings to m1
        m1 = new MathContext(50);

        // Displaying the result
        System.out.println(m1.getPrecision());
    }
}
```

**Output:**

```
50

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/math/mathcontext . html # getPrecision()](https://docs.oracle.com/javase/7/docs/api/java/math/MathContext.html#getPrecision())