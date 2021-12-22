# 选择 Java 中的下一个双(双，布尔)方法，示例

> 原文:[https://www . geeksforgeeks . org/choice format-next double-boolean-in-Java-method-with-examples/](https://www.geeksforgeeks.org/choiceformat-nextdoubledouble-boolean-method-in-java-with-examples/)

[**Java . text . choice format**](https://www.geeksforgeeks.org/tag/java-choiceformat/)类的 **nextDouble(double，boolean)** 方法用于在传递的布尔值为真时获取刚好大于传递的双精度值的双精度值，或者在传递的布尔值为假时返回刚好小于传递的双精度值的双精度值。

**语法:**

```java
public static double nextDouble(double d, boolean positive)
```

**参数**:该方法接受如下参数

*   **d:-** 它需要两倍的值，这个值的大小刚好可以找到。
*   **正数:-** 取布尔值，检查返回的双精度值是大还是小。

**返回值:**如果传递的布尔值为真，该方法返回的**双精度值**刚好大于传递的双精度值；如果传递的布尔值为假，该方法返回的双精度值刚好小于传递的双精度值。

以下是说明 **nextDouble()** 方法的示例:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// nextDouble() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // getting double value just
        // greater than the passed value
        // using nextDouble() method
        double value
            = ChoiceFormat.nextDouble(22, false);

        // display the result
        System.out.print("Next Double value : "
                         + value);
    }
}
```

**Output:** 

```java
Next Double value : 21.999999999999996
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// nextDouble() method

import java.text.*;
import java.util.*;
import java.io.*;

public class GFG {
    public static void main(String[] argv)
    {
        // calling getValue() method
        getValue(1.23d, true);
        getValue(10d, false);
        getValue(-12d, true);
        getValue(1.2f, false);
        getValue(50, true);
    }

    // defining getValue() method
    public static void getValue(double doub,
                                boolean bool)
    {

        // getting double value just
        // greater than the passed value
        // using nextDouble() method
        double value
            = ChoiceFormat.nextDouble(doub, bool);

        // display the result
        if (bool)
            System.out.println("Just greater than "
                               + doub + ": "
                               + value);
        else
            System.out.println("Just lesser than "
                               + doub + ": "
                               + value);
    }
}
```

**Output:** 

```java
Just greater than 1.23: 1.2300000000000002
Just lesser than 10.0: 9.999999999999998
Just greater than -12.0: -11.999999999999998
Just lesser than 1.2000000476837158: 1.2000000476837156
Just greater than 50.0: 50.00000000000001
```

**参考:**T2【https://docs . Oracle . com/javase/9/docs/API/Java/text/choice format . html # next double-double-boolean-T4】