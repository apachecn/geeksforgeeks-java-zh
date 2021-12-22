# MathContext 等于()Java 中的方法

> 原文:[https://www . geesforgeks . org/math context-equals-method-in-Java/](https://www.geeksforgeeks.org/mathcontext-equals-method-in-java/)

**java . math . MathContext . equals()**是 Java 中的内置函数，它检查这个 math context 对象与作为参数传递给函数的对象之间的相等性。如果上述两个对象的上下文设置相同，则该函数返回 true。

**语法:**

```
public boolean equals(Object obj)
```

**参数:**该函数接受一个对象*对象*作为强制参数，使用该参数检查数学上下文是否相等。

**返回值:**当且仅当指定的对象是与该对象具有相同上下文设置的 MathContext 对象时，该方法返回 true。

**示例:**

```
Input : m1 = new MathContext(2, RoundingMode.UP), 
        m2 = new MathContext(2, RoundingMode.HALF_UP)
Output : false

Input :  m1 = new MathContext(2), 
         m2 = new MathContext(2, RoundingMode.HALF_UP)
Output : true

```

下面的程序将说明 Java . math . mathcontext . equals():
**程序 1 :**

```
// Java program to demonstrate equals() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating 2 MathContext objects m1 and m2
        MathContext m1, m2;

        // Assigning context settings to m1, m2
        m1 = new MathContext(2);
        m2 = new MathContext(2, RoundingMode.FLOOR);

        // Displaying the result
        System.out.println(m1.equals(m2));
    }
}
```

**Output:**

```
false

```

**程序 2 :**

```
// Java program to demonstrate equals() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating 2 MathContext objects m1 and m2
        MathContext m1, m2;

        // Assigning context settings to m1, m2
        m1 = new MathContext(2);
        m2 = new MathContext(2, RoundingMode.HALF_UP);

        // Displaying the result
        System.out.println(m1.equals(m2));
    }
}
```

**Output:**

```
true

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/mathcontext . html # equals(Java . lang . object)](https://docs.oracle.com/javase/7/docs/api/java/math/MathContext.html#equals(java.lang.Object))