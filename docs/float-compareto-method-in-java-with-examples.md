# Java 中的 Float compareTo()方法，带示例

> 原文:[https://www . geesforgeks . org/float-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/float-compareto-method-in-java-with-examples/)

[**Float 类**](https://www.geeksforgeeks.org/java-lang-float-class-in-java/) 的**compreto()**方法是 Java 中的一个内置方法，用于比较两个指定的 Float 值。返回的整数值的符号与函数调用返回的整数的符号相同。

**语法:**

```
public int compareTo(Object f)

```

**参数:**该函数接受一个强制参数对象 **f** ，它是要比较的值。

**返回值:**该函数返回如下值:

*   **等于 0:** 对象 f 等于自变量对象
*   **小于 0:** 对象 f 小于自变量对象
*   **大于 0:** 对象 f 大于自变量对象

下面的程序说明了 Float.compareTo()函数的使用:

**程序 1:** 当两个整数相同时

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate
// the Float.compareTo() method

import java.lang.Float;

public class GFG {
    public static void main(String[] args)
    {

        // Get the two float values
        // to be compared
        Float f1 = 1023f;
        Float f2 = 1023f;

        // function call to compare two float values
        if (f1.compareTo(f2) == 0) {

            System.out.println("f1=f2");
        }
        else if (f1.compareTo(f2) < 0) {

            System.out.println("f1<f2");
        }
        else {

            System.out.println("f1>f2");
        }
    }
}
```

**Output:** 

```
f1=f2

```

**程序 2 :** 当 f1 < f2

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate
// the Float.compareTo() method

import java.lang.Float;

public class GFG {
    public static void main(String[] args)
    {

        // Get the two float values
        // to be compared
        Float f1 = 10f;
        Float f2 = 1023f;

        // function call to compare two float values
        if (f1.compareTo(f2) == 0) {

            System.out.println("f1=f2");
        }
        else if (f1.compareTo(f2) < 0) {

            System.out.println("f1<f2");
        }
        else {

            System.out.println("f1>f2");
        }
    }
}
```

**Output:** 

```
f1

```

**程序 3:** 当 f1 > f2

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to illustrate
// the Float.compareTo() method

import java.lang.Float;

public class GFG {
    public static void main(String[] args)
    {

        // Get the two float values
        // to be compared
        Float f1 = 1023f;
        Float f2 = 10f;

        // function call to compare two float values
        if (f1.compareTo(f2) == 0) {

            System.out.println("f1=f2");
        }
        else if (f1.compareTo(f2) < 0) {

            System.out.println("f1<f2");
        }
        else {

            System.out.println("f1>f2");
        }
    }
}
```

**Output:** 

```
f1>f2

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/lang/float . html # compare to(Java . lang . float)](https://docs.oracle.com/javase/7/docs/api/java/lang/Float.html#compareTo(java.lang.Float))