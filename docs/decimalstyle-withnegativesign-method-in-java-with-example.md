# Java 中的带否定设计()方法的十进制样式，示例

> 原文:[https://www . geeksforgeeks . org/decimal style-with negative design-method-in-Java-with-example/](https://www.geeksforgeeks.org/decimalstyle-withnegativesign-method-in-java-with-example/)

java 中**Java . time . format . DecimalStyle 类**的**with negative design()**方法用于设置用于表示此 decimal style 区域设置负号的字符。此方法将字符作为参数，并返回带有更新的负号字符的十进制样式实例。

**语法:**

```
public DecimalStyle withNegativeSign(char negativeSign)

```

**参数:**该方法接受**否定设计**作为参数，该参数是将用于表示该十进制样式的负号的字符。

**返回值:**该方法返回带有更新负号字符的**十进制样式**实例。

**异常:**这个方法不抛出任何异常。

**程序:**

```
// Java program to demonstrate
// the above method

import java.time.format.*;
import java.util.*;

public class DecimalStyleDemo {
    public static void main(String[] args)
    {

        DecimalStyle ds
            = DecimalStyle.STANDARD;

        System.out.println("Current Character"
                           + " used for negative sign: "
                           + ds.getNegativeSign());

        char negativeSign = '*';

        ds = ds.withNegativeSign(negativeSign);

        System.out.println("Updated Character "
                           + "used for negative sign: "
                           + ds.getNegativeSign());
    }
}
```

**输出:**

```
Current Character used for negative sign: -
Updated Character used for negative sign: *

```

**参考:**T2【https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimal style . html # with negative design(char)