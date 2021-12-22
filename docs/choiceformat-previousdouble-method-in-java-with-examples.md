# 选择 Java 中的 Format previousDouble()方法，示例

> 原文:[https://www . geesforgeks . org/choice format-previous double-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-previousdouble-method-in-java-with-examples/)

[**Java . text . choice format**](https://www.geeksforgeeks.org/tag/java-choiceformat/)类的 **previousDouble()** 方法用于获取仅小于传递的双精度值的双精度值。
**语法:**

```java
public static final double previousDouble(double d)
```

**参数**:该方法接受双精度值 **d** 作为参数，返回之前的双精度值。
**返回值:**这个方法返回一个**的双精度值**刚好小于传递的双精度值。
以下是举例说明 **previousDouble()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// previousDouble() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // getting double value just
        // lesser than the passed value
        // using previousDouble() method
        double value
            = ChoiceFormat.previousDouble(22);

        // display the result
        System.out.print("Lesser double value: "
                         + value);
    }
}
```

**Output:** 

```java
Lesser double value: 21.999999999999996
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// previousDouble() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // calling getValue() method
        getValue(1.23d);
        getValue(10d);
        getValue(-12d);
        getValue(1.2f);
        getValue(50);
    }

    // defining getValue() method
    public static void getValue(double doub)
    {

        // getting double value just
        // lesser than the passed value
        // using previousDouble() method
        double value
            = ChoiceFormat.previousDouble(doub);

        // display the result
        System.out.println("Just lesser than "
                           + doub + ": "
                           + value);
    }
}
```

**Output:** 

```java
Just lesser than 1.23: 1.2299999999999998
Just lesser than 10.0: 9.999999999999998
Just lesser than -12.0: -12.000000000000002
Just lesser than 1.2000000476837158: 1.2000000476837156
Just lesser than 50.0: 49.99999999999999
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/choice format . html # previous double-double-T4】