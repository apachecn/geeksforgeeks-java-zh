# 带下划线的 Java 数值文字

> 原文:[https://www . geesforgeks . org/Java-数字-文字-带下划线/](https://www.geeksforgeeks.org/java-numeric-literals-with-underscore/)

JDK 7 引入了一个新特性，允许使用下划线字符书写数字。数字文字被打破，以增强可读性。该功能用于分隔数字文字中的一组数字，可以提高源代码的可读性。在使用数字文字之前，程序员必须遵循一些规则，例如

1.我们不应该在整数之前或之后使用下划线。

```
int p = _10; // Error, this is an identifier, not a numeric literal  
int p = 10_; // Error, cannot put underscores at the end of a number  
```

2.我们不应该在浮点文本中的小数点前后使用下划线。

```
float a = 10._0f; // Error, cannot put underscores adjacent to a decimal point  
float a = 10_.0f; // Error, cannot put underscores adjacent to a decimal point  
```

3.我们不应该在长整数和浮点整数中分别使用在 L 或 F 之前的后缀。

```
long a = 10_100_00_L; // Error, cannot put underscores prior to an L suffix  
float a = 10_100_00_F; // Error, cannot put underscores prior to an F suffix  
```

4.我们不能在需要一串数字的位置使用下划线。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate Numeric Literals with
// Underscore

public class Example {
    public static void main(String args[])
    {
        // Underscore in integral literal
        int a = 7_7;
        System.out.println("The value of a is=" + a);

        // Underscore in floating literal
        double p = 11.239_67_45;
        System.out.println("The value of p is=" + p);

        float q = 16.45_56f;
        System.out.println("The value of q is=" + q);

        // Underscore in binary literal
        int c = 0B01_01;
        System.out.println("c = " + c);

        // Underscore in hexadecimal literal
        int d = 0x2_2;
        System.out.println("d = " + d);

        // Underscore in octal literal
        int e = 02_3;
        System.out.println("e = " + e);
    }
}
```

**Output**

```
The value of a is=77
The value of p is=11.2396745
The value of q is=16.4556
c = 5
d = 34
e = 19

```