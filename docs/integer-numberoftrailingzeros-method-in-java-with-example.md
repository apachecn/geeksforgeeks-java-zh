# Java 中的整数. numberOfTrailingZeros()方法，示例

> 原文:[https://www . geesforgeks . org/integer-number of trailing zeros-in-Java-method-with-example/](https://www.geeksforgeeks.org/integer-numberoftrailingzeros-method-in-java-with-example/)

**Java . lang . integer . number of trailing zeros()**是返回最低位(即)之后的零(0)位总数的方法。最右边或最低有效的“1”位)指定整数值的二进制补码表示中的一位，或者我们可以说它是将 int 值转换为 binary 的函数，然后考虑最低的一位，并返回其后面的零位数。如果指定的整数值在其二进制补码表示中没有一位，换句话说，如果它等于零，那么它将返回 32。

**语法:**

```java
public static int numberOfTrailingZeros(int a)
```

**参数:**参数 *a* 为整数值。

**返回值:**该方法返回指定 int 值的二进制补码二进制表示中最低一位或设置位之后的零位数，如果该值等于零，则返回 32。

**解释**

*   考虑 a = 170 的整数
*   二进制表示= 10101010
*   最低一位= 2
*   尾随零的数量= 1

下面的程序说明了 Java . lang . integer . numberoftrailingzeros()方法。

**程序 1:** 为正数。

```java
// Java program to illustrate the
// Java.lang.Integer.numberOfTrailingZeros() method
import java.lang.*;

public class TrailingZeros {

public static void main(String[] args) {

    int a = 155;
    System.out.println("Integral Number = " + a);

    // Returns the number of zero bits following the lowest-order 
        //rightmost one-bit 
    System.out.print("Number of Trailing Zeros = ");
    System.out.println(Integer.numberOfTrailingZeros(a));
         a = 24;
    System.out.println("Integral Number = " + a);

    // Returns the number of zero bits following the lowest-order 
    //rightmost one-bit 
    System.out.print("Number of Trailing Zeros = ");
    System.out.println(Integer.numberOfTrailingZeros(a));

}
}
```

**Output:**

```java
Integral Number = 155
Number of Trailing Zeros = 0
Integral Number = 24
Number of Trailing Zeros = 3

```

**注意:**这里尾随零的数量等于 0，表示 155，这是因为在二进制表示 10011011 中，没有零跟随最低阶(即。最右边或最低有效“1”位)一位。

**程序 2:** 为负数。

```java
// Java program to illustrate the
// Java.lang.Integer.numberOfTrailingZeros() method
import java.lang.*;

public class TrailingZeros {

public static void main(String[] args) {

    int a = -1;
    System.out.println("Integral Number = " + a);

    // Returns the number of zero bits following the lowest-order 
    //rightmost one-bit 
    System.out.print("Number of Trailing Zeros = ");
    System.out.println(Integer.numberOfTrailingZeros(a));
        a = -90;
    System.out.println("Integral Number = " + a);

    // Returns the number of zero bits following the lowest-order 
    //rightmost one-bit 
    System.out.print("Number of Trailing Zeros = ");
    System.out.println(Integer.numberOfTrailingZeros(a));

}
}
```

**Output:**

```java
Integral Number = -1
Number of Trailing Zeros = 0
Integral Number = -90
Number of Trailing Zeros = 1

```

**程序 3:** 为十进制值。
**注意:**当十进制值作为参数传递时，它会返回一条错误消息。

```java
// Java program to illustrate the
// Java.lang.Integer.numberOfTrailingZeros() method
import java.lang.*;

public class TrailingZeros {

public static void main(String[] args) {

     System.out.println("Number of trailing zeros = "+
     Integer.numberOfTrailingZeros(12.66));

}
}
```

**输出:**

```java
prog.java:10: error: incompatible types: possible lossy conversion from double to int
     Integer.numberOfTrailingZeros(12.66));
                                   ^
Note: Some messages have been simplified; recompile with 
-Xdiags:verbose to get full output
1 error

```

**程序 4:** 为字符串值。
**注意:**当字符串值作为参数传递时，它会返回一条错误消息。

```java
// Java program to illustrate the
// Java.lang.Integer.numberOfTrailingZeros() method
import java.lang.*;

public class TrailingZeros {

public static void main(String[] args) {

 System.out.println("Number of trailing zeros = "
                           + Integer.numberOfTrailingZeros("12"));
}
}
```

**输出:**

```java
prog.java:10: error: incompatible types: String cannot be converted to int
                           + Integer.numberOfTrailingZeros("12"));
                                                           ^
Note: Some messages have been simplified; recompile with 
-Xdiags:verbose to get full output
1 error

```