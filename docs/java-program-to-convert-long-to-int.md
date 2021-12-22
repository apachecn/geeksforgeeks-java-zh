# 将长整型转换为整型的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-long-to-int/](https://www.geeksforgeeks.org/java-program-to-convert-long-to-int/)

Long 是一种比 int 更大的**数据类型，我们需要显式地对转换执行类型转换。类型转换是通过类型转换运算符执行的。将 long 转换为 int 基本上有**三种**方法:**

1.  通过**型铸造**
2.  使用**来检测()**方法
3.  使用长包装类的 **intValue()** 方法。

**1。使用显式铸造**

在类型转换中，程序员在程序设计过程中使用转换操作符将一种数据类型转换成另一种数据类型。在类型转换中，当将数据类型转换为另一种数据类型时，目标数据类型可能小于源数据类型，这就是为什么它也被称为收缩转换。

**语法/声明:**

```java
destination_datatype = (target_datatype)variable;

() is a casting operator.
```

**target_datatype:** 是我们要转换源数据类型的数据类型。

**型铸造示例:**

```java
float x;
byte y;
...
...
y=(byte)x;
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert long to int

import java.util.*;
class GFG {
    public static void main(String[] args)
    {

        // long value
        long longnum = 10000;

        // explicit type casting from long to int
        int intnum = (int)longnum;

        System.out.println("Converted type: "+ ((Object)intnum).getClass().getName());
        System.out.println("Converted int value is: "
                           + intnum);
    }
}
```

**Output**

```java
Converted type: java.lang.Integer
Converted int value is: 10000
```

**2。使用** [**至**](https://www.geeksforgeeks.org/java-math-tointexactlong-value-method/) **方法**

**语法:**

```java
public static int toIntExact(long value)

```

**参数:**

*   **值:**长值

**返回:**
该方法将输入参数作为 int(整数)返回。

**异常:**
它抛出**算术异常**——如果结果溢出一个整数

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert long to int

class Main {
  public static void main(String[] args) {

    // create long variable
    long value1 = 523386L;
    long value2 = -4456368L;

    // change long to int
    int num1 = Math.toIntExact(value1);
    int num2 = Math.toIntExact(value2);

    // print the type
    System.out.println("Converted type: "+ ((Object)num1).getClass().getName());
    System.out.println("Converted type: "+ ((Object)num2).getClass().getName());

    // print the int value
    System.out.println(num1);  // 52336
    System.out.println(num2);  // -445636
  }
}
```

**Output**

```java
Converted type: java.lang.Integer
Converted type: java.lang.Integer
523386
-4456368
```

**3。使用**[**intValue()**](https://www.geeksforgeeks.org/integer-intvalue-method-in-java/)T6】法的龙包装纸类

**语法:**

```java
public int intValue()
```

**参数:**该方法不接受任何参数。

**返回值:**该方法返回转换为整数类型后由对象表示的数值。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to convert long to int using intValue()
// method

class GFG {
    public static void main(String[] args)
    {
        // Long object
        Long longnum = 100L;

        // Converting Long object to int primitive type
        int intnum = longnum.intValue();

        // printing the type
        System.out.println("Converted type: "
            + ((Object)intnum).getClass().getName());

        // printing the int value
        System.out.println("Converted int value: "
                           + intnum);
    }
}
```

**Output**

```java
Converted type: java.lang.Integer
Converted int value: 100
```