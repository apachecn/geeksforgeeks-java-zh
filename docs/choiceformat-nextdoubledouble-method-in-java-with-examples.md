# 用示例选择 Java 中的 nextDouble(双)方法

> 原文:[https://www . geeksforgeeks . org/choice format-next double-method-in-Java-with-examples/](https://www.geeksforgeeks.org/choiceformat-nextdoubledouble-method-in-java-with-examples/)

[**Java . text . choice format**](https://www.geeksforgeeks.org/tag/java-choiceformat/)类的 **nextDouble(Double)** 方法用于获取刚好大于指定 double 值的 double 值。

**语法:**

```
public static final double nextDouble(double d)
```

**参数**:该方法接受双精度值 **d** 作为参数，返回下一个双精度值。
**返回值:**这个方法返回一个**的双精度值**刚好大于传递的双精度值。
以下是举例说明 **nextDouble()** 方法:
**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
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
            = ChoiceFormat.nextDouble(22);

        // display the result
        System.out.print("Next greater double"
                         + " value than 22: "
                         + value);
    }
}
```

**Output:** 

```
Next greater double value than 22: 22.000000000000004
```