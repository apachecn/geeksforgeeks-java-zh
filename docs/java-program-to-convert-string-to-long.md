# 将字符串转换为长字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-convert-string-to-long/](https://www.geeksforgeeks.org/java-program-to-convert-string-to-long/)

给定一个字符串，任务是在 Java 中将给定的字符串转换为 Long。

**示例:**

```java
Input : String = "20"
Output: 20

Input : String = "999999999999"
Output: 999999999999
```

**字符串:**Java 中的字符串是内部由字符数组支持的对象。由于数组是不可变的，而字符串也是一种保存字符的特殊数组，因此字符串也是不可变的。

**Long:** 长数据类型是 64 位二进制补码整数。其值范围介于(-2 <sup>63</sup> )至(2 <sup>63</sup> -1)(含)之间。其默认值为 0。当您需要的值范围超过 int 提供的值范围时，可以使用长数据类型。

### 方法

在 Java 中，有许多方法可以将字符串转换为长数据类型。下面列出了其中的一些。

*   使用 Long.parseLong()方法
*   使用 Long.valueOf()方法
*   使用长类构造函数

### 1.使用 Long.parseLong()方法

Long.parseLong()方法是一种方法，其中字符串中的所有字符都必须是数字，除了第一个字符，第一个字符可以是数字或减号“-”。

**语法:**

```java
Long varLong=Long.parseLong(str);
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert String to Long 
// using parseLong() 

public class GFG { 

    // main method 
    public static void main(String args[]) 
    { 

        // create a String 
        String str = "999999999999"; 
          System.out.println("String - " + str); 

        // convert into Long 
        long varLong = Long.parseLong(str); 

        // print String as Long 
        System.out.println("Long - " + varLong); 
    } 
}
```

**Output**

```java
String - 999999999999
Long - 999999999999
```

### 2.使用 Long.valueOf()方法

Long.valueOf()方法是将字符串转换为长值的方法。与 parseLong(String)方法类似，该方法也允许将减号“-”作为字符串中的第一个字符。

**语法:**

```java
long varLong = Long.valueOf(str);
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert String to Long
// using valueOf() 

public class GFG { 

    // main method 
    public static void main(String args[]) 
    { 

        // create a String 
        String str = "999999999999"; 
          System.out.println("String - " + str);

        // convert into Long
        long varLong = Long.valueOf(str); 

        // print String as Long
        System.out.println("Long - " + varLong); 
    } 
}
```

**Output**

```java
String - 999999999999
Long - 999999999999
```

### 3.使用长类构造函数

long 类有一个构造函数，它允许 String 参数，并创建一个新的 long 对象，该对象用等效的 Long 值表示指定的字符串。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import java.util.*;
import java.io.*;

class GFG {
    public static void main (String[] args) {

       String str = "999999999";
       System.out.println("String - " + str);

       //Conversion using Long(String s) constructor
       long num = new Long(str);

       System.out.println("Long - " + num);
    }
}
```

**输出**

```java
String - 999999999
Long - 999999999
```