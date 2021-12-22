# 在 Java 中将双精度转换为整数

> 原文:[https://www . geesforgeks . org/convert-Java 中的双精度转换为整数/](https://www.geeksforgeeks.org/convert-double-to-integer-in-java/)

给定一个双实数。编写一个 Java 程序，将给定的双精度数转换成 Java 中的整数(int)。

**示例:**

```
Input: double = 3452.234
Output: 3452

Input: double = 98.23
Output: 98
```

**Double:**Double 数据类型是双精度 64 位 IEEE 754 浮点。它的价值范围是无穷无尽的。双数据类型通常用于十进制值，就像浮点一样。双精度数据类型也不应用于精确值，如货币。其**默认值为 0.0** 。

**例:**双 d1 = 10.5

**整数:**整数或 int 数据类型是一个 32 位有符号二进制补码整数。它的取值范围在–2，147，483，648 (-2^31)到 2，147，483，647 (2^31 -1)(含)之间。其最小值为–2，147，483，648，最大值为 2，147，483，647。其**默认值为 0** 。int 数据类型通常用作整数值的默认数据类型，除非内存没有问题。

**示例:** int a = 10

### 方法

有许多方法可以将 Double 数据类型转换为 Integer (int)数据类型。下面列出了其中的一些。

*   使用**类型铸造**
*   使用 **Double.intValue()** 方法
*   使用 **Math.round()** 方法**T3】**

### **方法 1–使用类型铸造**

这种技术非常简单，用户友好。

**语法–**

```
double data = 3452.345
int value = (int)data;
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert Double to
// int using Typecasting

public class GFG {

    // main method
    public static void main(String args[])
    {

        // Get the double value
        double data = 3452.345;
        System.out.println("Double - " + data);

        // convert into int
        int value = (int)data;

        // print the int value
        System.out.println("Integer - " + value);
    }
}
```

**Output**

```
Double - 3452.345
Integer - 3452
```

### 方法 2–使用 Double.intValue()方法

这种技术类似于类型转换方法。类型转换方法和此方法的主要区别在于类型转换方法是显式方法，此方法是 Wrapper 类 Double 截断小数点后的所有数字。

**语法:**

```
double data = 3452.345
Double newData = new Double(data);
int value = newData.intValue();
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert Double to int
// using using Double.intValue()
public class GFG {

    // main method
    public static void main(String args[])
    {

        // Get the double value
        Double data = 3452.345;
        System.out.println("Double - " + data);
        // Create a wrapper around
        // the double value
        Double newData = new Double(data);

        // convert into int
        int value = newData.intValue();

        // print the int value
        System.out.println("Double - " + value);
    }
}
```

**输出**

```
Double - 3452.345
Double - 3452
```

### 方法 3–使用数学圆()方法

**Math.round()** 接受一个双精度值，并通过将该值加 0.5 并修剪其小数点将其转换为最近的长值。然后可以使用类型转换将长值转换为 int。

**语法:**

```
long Math.Round(Double doubleValue);
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert Double to int
// using Math.round()

public class GFG {

    // main method
    public static void main(String args[])
    {

        // Get the double value
        double data1 = 3452.345;
        System.out.println("Double : " + data1);

        // convert into int
        int value1 = (int)Math.round(data1);

        // print the int value
        System.out.println("Integer : " + value1);

          double data2 = 3452.765;
        System.out.println("\nDouble : " + data2);

        // convert into int
        int value2 = (int)Math.round(data2);

        // print the int value
        System.out.println("Integer : " + value2);
    }
}
```

**Output**

```
Double : 3452.345
Integer : 3452

Double : 3452.765
Integer : 3453
```

> **注意–**这里可以看到 Math.round()方法通过将数字四舍五入为最接近的整数，将双精度转换为整数。
> 
> 例如–**10.6**将使用 Math.round() 方法转换为 **11，1 将使用 typecasting 或 Double.intValue()方法**转换为 **10。**