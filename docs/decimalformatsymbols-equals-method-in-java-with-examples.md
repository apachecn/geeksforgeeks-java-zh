# Java 中的十进制格式符号等于()方法，示例

> 原文:[https://www . geesforgeks . org/decimal format symbols-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/decimalformatsymbols-equals-method-in-java-with-examples/)

**等于()**的**法。Java 中的抽取格式符号类**用于检查该抽取格式符号与指定的抽取格式符号是否相等。此方法获取一个十进制格式符号实例，并将其与该十进制格式符号进行比较，然后返回一个表示相同内容的布尔值。

**语法:**

```java
public boolean equals(Object obj)

```

**参数:**该方法接受一个参数**对象**，该参数是要检查与该十进制格式符号是否相等的十进制格式符号。

**返回值:**这个方法返回一个**布尔**，告诉这个十进制格式符号是否等于指定的对象。

**异常:**这个方法不抛出任何异常。

**程序:**

```java
// Java program to demonstrate
// the above method

import java.text.*;
import java.util.*;

public class DecimalFormatSymbolsDemo {
    public static void main(String[] args)
    {

        DecimalFormatSymbols dfs1
            = new DecimalFormatSymbols();

        System.out.println("DecimalFormatSymbols 1: "
                           + dfs1);

        DecimalFormatSymbols dfs2
            = new DecimalFormatSymbols(
                new Locale("JAPANESE"));

        System.out.println("DecimalFormatSymbols 2: "
                           + dfs2);

        DecimalFormatSymbols dfs3
            = (DecimalFormatSymbols)dfs1.clone();

        System.out.println("DecimalFormatSymbols 3: "
                           + dfs3);

        System.out.println("Comparing DFS 1 and DFS 2: "
                           + dfs1.equals(dfs2));

        System.out.println("Comparing DFS 2 and DFS 3: "
                           + dfs2.equals(dfs3));

        System.out.println("Comparing DFS 1 and DFS 3: "
                           + dfs1.equals(dfs3));
    }
}
```

**输出:**

```java
DecimalFormatSymbols 1: java.text.DecimalFormatSymbols@1073a
DecimalFormatSymbols 2: java.text.DecimalFormatSymbols@1073a
DecimalFormatSymbols 3: java.text.DecimalFormatSymbols@1073a
Comparing DFS 1 and DFS 2: false
Comparing DFS 2 and DFS 3: false
Comparing DFS 1 and DFS 3: true

```

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/text/decimalformatsymbols . html # equals-Java . lang . object-](https://docs.oracle.com/javase/9/docs/api/java/text/DecimalFormatSymbols.html#equals-java.lang.Object-)