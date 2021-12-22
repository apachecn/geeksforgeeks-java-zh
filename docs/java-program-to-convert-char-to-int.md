# 将字符转换为整数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-char-to-int/](https://www.geeksforgeeks.org/java-program-to-convert-char-to-int/)

在 Java 中给定一个字符，您的任务是编写一个 Java 程序，将这个给定的字符转换成一个整数。

**示例:**

```
Input: ch = '3'
Output: 3

Input: ch = '9'
Output: 9
```

**整数:**整数或 int 数据类型是一个 32 位有符号二进制补码整数。它的取值范围在–2，147，483，648 (-2^31)到 2，147，483，647 (2^31 -1)(含)之间。其最小值为–2，147，483，648，最大值为 2，147，483，647。其**默认值为 0** 。int 数据类型通常用作整数值的默认数据类型，除非内存没有问题。

```
Example: int a = 10
```

**字符:**字符数据类型是单个 16 位 Unicode 字符。它的取值范围在' \u0000 '(或 0)到' \ uffff '(或 65，535，含)之间。字符数据类型用于存储字符。

```
Example: char ch = 'c'
```

### 方法

有许多方法可以将字符数据类型转换为整数(整数)数据类型。下面列出了其中的一些。

*   使用 ASCII 值
*   使用 String.valueOf()方法
*   使用 Character.getNumericValue()方法

### **1。使用 ASCII 值**

此方法使用类型转换来获取给定字符的 ASCII 值。相应的整数通过从 ASCII 值 0 中减去 ASCII 值来计算。换句话说，这个方法通过找到这个字符的 ASCII 值和 0 的 ASCII 值之间的差异，将字符转换为 int。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert
// char to int using ASCII value

class GFG {
    public static void main(String[] args)
    {

        // Initializing a character(ch)
        char ch = '3';
        System.out.println("char value: " + ch);

        // Converting ch to it's int value
        int a = ch - '0';
        System.out.println("int value: " + a);
    }
}
```

**Output**

```
char value: 3
int value: 3
```

### **2。使用 String.valueOf()** 方法

字符串类的方法 valueOf()可以将各种类型的值转换为字符串值。它可以将 int、char、long、boolean、float、double、object、char 数组转换为 String，使用[integer . parsent()](https://www.geeksforgeeks.org/string-to-integer-in-java-parseint/)方法可以将 String 转换为 int 值。下面的程序演示了 valueOf()方法的使用。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert
// char to int using String.valueOf()

class GFG {
    public static void main(String[] args)
    {
        // Initializing a character(ch)
        char ch = '3';
        System.out.println("char value: " + ch);

        // Converting the character to it's int value
        int a = Integer.parseInt(String.valueOf(ch));
        System.out.println("int value: " + a);
    }
}
```

**Output**

```
char value: 3
int value: 3
```

### **3。使用 Character.getNumericValue()方法**

Character 类的 getNumericValue()方法用于获取任意特定字符的整数值。例如，字符“9”将返回一个值为 9 的 int。下面的程序说明了 getNumericValue()方法的使用。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert char to int
// using Character.getNumericValue()

class GFG {
    public static void main(String[] args)
    {

        // Initializing a character(ch)
        char ch = '3';
        System.out.println("char value: " + ch);

        // Converting the Character to it's int value
        int a = Character.getNumericValue(ch);
        System.out.println("int value: " + a);
    }
}
```

**Output**

```
char value: 3
int value: 3
```