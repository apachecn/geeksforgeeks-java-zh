# Java 中的 FormatStyle values()方法，示例

> 原文:[https://www . geesforgeks . org/format style-values-method-in-Java-with-examples/](https://www.geeksforgeeks.org/formatstyle-values-method-in-java-with-examples/)

**FormatStyle 枚举**的**值()**方法用于包含该 FormatStyle 的单位的数组，按照它们被声明的顺序。
**语法:**

```
public static FormatStyle[] values()
```

**参数:**此方法不接受任何内容。
**返回值:**这个方法返回一个包含这个枚举类型常量的**数组，按照它们被声明的顺序。
下面的程序说明了 FormatStyle.values()方法:
**程序 1:**** 

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// FormatStyle.values() method

import java.time.format.FormatStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get FormatStyle instance
        FormatStyle formatStyle
            = FormatStyle.valueOf("FULL");

        // Get the constants using values()
        FormatStyle[] array
            = formatStyle.values();

        // Print the values
        for (int i = 0; i < array.length; i++)
            System.out.println(array[i]);
    }
}
```

**Output:** 

```
FULL
LONG
MEDIUM
SHORT
```

**节目 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// FormatStyle.values() method

import java.time.format.FormatStyle;

public class GFG {
    public static void main(String[] args)
    {

        // Get FormatStyle instance
        FormatStyle formatStyle
            = FormatStyle.valueOf("FULL");

        // Get the constants using values()
        FormatStyle[] array
            = formatStyle.values();

        // Print the values
        System.out.println("FormatStyle length: "
                           + array.length);
    }
}
```

**Output:** 

```
FormatStyle length: 4
```

参考文献:[https://docs . Oracle . com/javase/10/docs/API/Java/time/format/format style . html](https://docs.oracle.com/javase/10/docs/api/java/time/format/FormatStyle.html)