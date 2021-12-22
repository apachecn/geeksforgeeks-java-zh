# Java.lang.Integer 类及其方法

> 原文:[https://www . geesforgeks . org/Java-lang-integer-class-methods/](https://www.geeksforgeeks.org/java-lang-integer-class-methods/)

整数将整数数据类型包装到一个对象中，该对象包含一个具有数据类型为 int 的字段。
**施工人员:**

*   整数:构造一个表示整数值的整数对象。
*   整数(字符串参数) :构造表示字符串值的字符串对象。

整数类方法:

1.  **toBinaryString():Java . lang . integer . toBinaryString()**方法将参数的整数值转换为字符串形式的 Binary 表示形式。
    **语法**

```
public static String toBinaryString(int arg)
Parameters
arg : integer argument whose Binary representation we want
Return
Binary representation of the argument.
```

2.  **bitcount():Java . lang . integer . bitcount()**
    方法将参数的整数值转换为 Binary 字符串，然后返回其中出现的 1 的个数。
    **语法**

```
public static int bitCount(int arg)
Parameters
arg : integer argument whose no. of 1's bit we want
Return
no. of 1's bit present in the argument.
```

2.  **to exstring():Java . lang . integer . to exstring()**方法将参数的整数值转换为字符串的十六进制表示形式。
    **语法**

```
public static String toHexString(int arg)
Parameters
arg : integer argument whose Hexadecimal representation we want
Return
Hexadecimal representation of the argument.
```

2.  **toOctalString():Java . lang . integer . to exstring()**方法将参数的整数值转换为字符串的十六进制表示形式。
    **语法**

```
public static String toHexString(int arg)
Parameters
arg : integer argument whose Hexadecimal representation we want
Return
Hexadecimal representation of the argument.
```

2.  **parse datatype():Java . lang . integer . parse _ _()**方法返回 argumented String 值的原始数据类型。
    基数(r)表示使用的编号格式位于字符串的基数“r”处。
    **语法**

```
public static int parseInt(String arg)
              or
public static int parseInt(String arg, int r)
Parameters
arg : argument passed
r : radix
Return
primitive data type of the argumented String value.
```

## Java 语言（一种计算机语言，尤用于创建网站）

```
// Java code explaining the Integer Class methods
// bitcount(), toBinaryString(), toHexString(), toOctalString(), parse__()
import java.lang.*;
public class NewClass
{
    public static void main(String args[])
    {
        int x = 15, count1, y = 128, count2;

        // Use of toBinaryString() method
        System.out.println("Binary string of 16 : "
                           + Integer.toBinaryString(x));
        System.out.println("Binary string of 100 : "
                           + Integer.toBinaryString(y));

        // Use of bitCount() method
        count1 = Integer.bitCount(x);
        System.out.println("\n 1's bit present in 16 : "+count1);

        count2 = Integer.bitCount(y);
        System.out.println(" 1's bit present in 100 : "+count2);

        // Use of toHexString() method
        System.out.println("\nHexadecimal string of 16 : "
                           + Integer.toHexString(x));
        System.out.println("Hexadecimal string of 100 : "
                           + Integer.toHexString(y));
        System.out.println("");

        // Use of toOctalString() method
        System.out.println("Octal string of 16 : "
                           + Integer.toOctalString(x));
        System.out.println("Octal string of 100 : "
                           + Integer.toOctalString(y) + "\n");

        // Use of parseInt() method
        int i1 =Integer.parseInt("34");
        int i2 = Integer.parseInt("15",8);
        double d = Double.parseDouble("54");

        System.out.println(i1);
        System.out.println(i2);
        System.out.println(d);
    }
}
```

1.  输出:

```
Binary string of 16   : 1111
Binary string of 100  : 10000000

 1's bit present in 16   : 4
 1's bit present in 100  : 1

Hexadecimal string of 16   : f
Hexadecimal string of 100  : 80

Octal string of 16   : 17
Octal string of 100  : 200

34
13
54.0
```

2.  **hashCode():Java . lang . integer . hashCode()**方法返回传递的参数的 [hashCode](https://en.wikipedia.org/wiki/Java_hashCode()) 值。
    **语法:**

```
public int hashCode(arg)
Parameters:
arg - the argument whose hashCode value we need
Returns:
hashCode value of arg
```

2.  **lowerstonebit():Java . lang . integer . lowerstonebit()**方法首先将 int 转换为 Binary，然后查找位于最低位置的 set(1)位，然后重置其余位
    例如 arg = 36
    它，s Binary presentation = 0010 0100
    它考虑最低位(位于 3)，现在重置其余位，即 0000 0100
    因此结果= 0100 即 4

```
public static int lowestOneBit(int arg)
**Parameters:**
arg - argument passed
**Returns:**
integer value by only considering lowest 1 bit in the argument.
```

2.  ****highestOneBit():Java . lang . integer . highestOneBit()**方法首先将 int 转换为 Binary，然后查找最低位置出现的 set(1)位，然后重置其余位
    例如 arg = 36
    它，s Binary presentation = 0010 0100
    它考虑最高位(位于 6)，现在重置其余位即 0001 0000
    因此结果= 10000 即 32**

```
public static int highestOneBit(int arg)
**Parameters:**
arg - argument passed
**Returns:**
integer value by only considering highest 1 bit in the argument.
```

## **Java 语言（一种计算机语言，尤用于创建网站）**

```
// Java program explaining Integer class methods
// hashcode(), lowestOneBit(), highestOneBit()
import java.lang.*;
public class NewClass
{
    public static void main(String[] args)
    {
        // Use of incrementExact() method
        int f1 = 30, f2 = -56;
        f1 = Integer.hashCode(f1);
        System.out.println("HashCode value of f1 : "+f1);

        f2 = Integer.hashCode(f2);
        System.out.println("HashCode value of f2 : "+f2);

        System.out.println("\nBinary representation of 30 : "
                           + Integer.toBinaryString(f1));

        // Use of lowestOneBit() method
        // Here it considers 00010 i.e. 2
        System.out.println("lowestOneBit of 30 : "
                           + Integer.lowestOneBit(f1));

        // Use of highestOneBit() method
        // Here it considers 10000 i.e. 16
        System.out.println("highestOneBit of 30 : "
                           + Integer.highestOneBit(f1));

    }
}
```

1.  **输出:** 

```
HashCode value of f1 : 30
HashCode value of f2 : -56

Binary representation of 30 : 11110
lowestOneBit of 30 : 2
highestOneBit of 30 : 16
```

2.  ****numberoftrainingzeros():Java . lang . integer . numberoftrainingzeros()**方法将 int 值转换为 Binary，然后考虑最低的一位，并返回其后的零位数。
    例如 arg = 36
    It，s 二进制表示= 0010 0100
    它认为最高位(在 6)即 0001 0000
    所以结果= 4
    **语法:**** 

```
public static int numberOfTrailingZeros(int arg)
**Parameters:**
arg - the argument
**Returns:**
Number of zero bits following the 1 bit at lowest position
```

2.  ****numberOfLeadingZeros():Java . lang . integer . numberOfLeadingZeros()**方法将 int 值转换为 Binary，然后考虑最高的一位并返回其前面的零位数。
    例如 arg = 36
    It，s 二进制表示= 0010 0100
    它认为最高位(在 6)即 0010 0000
    所以结果= 32–6 即 26
    **语法:**** 

```
public static int numberOfLeadingZeros(int arg)
**Parameters:**
arg - the argument
**Returns:**
Number of zero bits preceding the 1 bit at highest position
```

2.  ****reverse():Java . lang . integer . reverse()**方法首先查找传递的参数的 2 的补语，并反转 2 的补语中的比特顺序。
    **语法:**** 

```
public static int reverse(int arg)
**Parameters:**
arg - the argument 
**Returns:**
int with reverse order of bits in 2's compliment of the passed argument
```

## **Java 语言（一种计算机语言，尤用于创建网站）**

```
// Java program explaining Integer class methods
// numberOfTrailingZeros(), numberOfLeadingZeros(), reverse()
import java.lang.*;
public class NewClass
{
    public static void main(String[] args)
    {
        int f1 = 30;

        // Binary representation of int arg for your understanding
        System.out.println("Binary representation of 30 : "
                           + Integer.toBinaryString(f1));

        // Use of numberOfTrailingZeros() method
        // No. of zeros following 1 in 00010 = 1
        System.out.println("\nNo. Of Trailing Zeros : "
                           + Integer.numberOfTrailingZeros(f1));

        // Use of highestOneBit() method
        // No. of zeros following 1 in 10000 i.e. 32 - 5 = 27
        System.out.println("\nNo. Of Leading Zeros : "
                           + Integer.numberOfLeadingZeros(f1));

        // Use of Reverse() method
        System.out.println("\nReverse : " + Integer.reverse(f1));
    }
}
```

1.  **输出:** 

```
Binary representation of 30 : 11110

No. Of Trailing Zeros : 1

No. Of Leading Zeros  : 27

Reverse : 2013265920
```

**本文由 **莫希特·古普塔** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。**