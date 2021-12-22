# Java 中的十进制样式等于()方法，示例

> 原文:[https://www . geesforgeks . org/decimal style-equals-method-in-Java-with-example/](https://www.geeksforgeeks.org/decimalstyle-equals-method-in-java-with-example/)

java 中**Java . time . format . DecimalStyle 类**的 **equals()** 方法用于检查这个 DecimalStyle 与指定的 decimal style 是否相等。此方法采用一个十进制样式实例，并将其与该十进制样式进行比较，然后返回一个表示相同内容的布尔值。

**语法:**

```
public boolean equals(Object obj)

```

**参数:**该方法接受一个参数**对象**，该参数是要检查是否与该十进制样式相等的十进制样式。

**返回值:**这个方法返回一个**布尔**，告诉这个十进制样式是否等于指定的对象。

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

        DecimalStyle ds1
            = DecimalStyle.STANDARD;

        DecimalStyle ds2
            = DecimalStyle.of(
                new Locale("ENGLISH"));

        DecimalStyle ds3 = null;

        System.out.println("Comparing DS 1 and DS 2: "
                           + ds1.equals(ds2));

        System.out.println("Comparing DS 2 and DS 3: "
                           + ds2.equals(ds3));

        System.out.println("Comparing DS 1 and DS 3: "
                           + ds1.equals(ds3));
    }
}
```

**输出:**

```
Comparing DS 1 and DS 2: true
Comparing DS 2 and DS 3: false
Comparing DS 1 and DS 3: false

```

**参考:**[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/decimal style . html # equals(Java . lang . object)](https://docs.oracle.com/javase/10/docs/api/java/time/format/DecimalStyle.html#equals(java.lang.Object))