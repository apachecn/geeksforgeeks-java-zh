# Java 中的 MathContext toString()方法

> 原文:[https://www . geesforgeks . org/math context-tostring-method-in-Java/](https://www.geeksforgeeks.org/mathcontext-tostring-method-in-java/)

**java . math . MathContext . tostring()**函数是 Java 中的内置函数，它返回 math context 对象的上下文设置的字符串表示形式。

返回的字符串将 MathContext 对象的设置表示为两个空格分隔的单词。这两个用空格分隔的字符串如下:

*   返回字符串的第一部分显示精度设置值，前面是字符串*“精度=*
*   返回字符串的第二部分显示了以字符串*“舍入模式=”(*)开头的舍入模式设置值

**语法:**

```java
public String toString()
```

**参数:**该方法不接受参数。

**返回值:**这个方法以上面提到的格式返回一个表示 MathContext 类的对象的上下文设置的字符串。

**示例:**

```java
Input : m1 = new MathContext(2, RoundingMode.HALF_DOWN)
Output : precision=2 roundingMode=HALF_DOWN

Input : m1 = new MathContext(60)
Output : precision=60 roundingMode=HALF_UP

```

下面的程序说明了 java.math.MathContext.toString()函数的使用:
**程序 1:**

```java
// Java program to demonstrate toString() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // creating a MathContext object
        MathContext m1;

        // assign context settings to m1
        m1 = new MathContext(37, RoundingMode.HALF_DOWN);

        System.out.println(m1.toString());
    }
}
```

**Output:**

```java
precision=37 roundingMode=HALF_DOWN

```

**程序 2:**

```java
// Java program to demonstrate toString() method
import java.math.*;
import java.io.*;

class GFG {
    public static void main(String[] args)
    {

        // Creating a MathContext object
        MathContext m1;

        // Assign context settings to m1
        m1 = new MathContext(60);

        System.out.println(m1.toString());
    }
}
```

**Output:**

```java
precision=60 roundingMode=HALF_UP

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/math/mathcontext . html # toString()](https://docs.oracle.com/javase/7/docs/api/java/math/MathContext.html#toString())