# Java 中使用 valueOf()方法的数据转换

> 原文:[https://www . geesforgeks . org/data-conversion-using-value of-method-Java/](https://www.geeksforgeeks.org/data-conversion-using-valueof-method-java/)

**valueOf()** 方法将数据从其内部形式转换为人类可读的形式。对于 Java 的所有内置类型，这是一个在字符串中重载的静态方法，因此每种类型都可以正确地转换为字符串。

当需要其他类型数据的字符串表示时调用，例如在串联操作中，你可以用任何数据类型调用这个方法，得到一个合理的字符串表示 **valueOf()** 返回 java.lang.Integer，它是整数的对象表示**value of()的几种形式:**

```
static String valueOf(int num)
static String valueOf(float num)
static String valueOf(boolean sta)
static String valueOf(double num)
static String valueOf(char[] data, int offset, int count)
static String valueOf(long num)
static String valueOf(Object ob)
static String valueOf(char chars[])
```

**返回:**

*   Returns the string representation of the given value.
*   **value of(iNum)；** //Returns the string representation of int iNum.
*   **string . value of(sta)；** //Returns the string representation of Boolean parameters.
*   **string . value of(fNum)；** //Returns the string representation of floating-point number fnum.
*   **String.valueof (data, 0,15);** //Returns the string representation of a specific subarray of chararray parameter.
*   **String.valueof (data, 0,5);** //Returns the string of charArray 0 to 5.
*   **String.valueof (data, 7,9);** //Returns a string with the starting index 7 of the character array, and the total count from 7 is 9.

**例 1:**

```
Input : 30
// concatenating  integer value with a String 
Output: 3091

Input : 4.56589
// concatenating  float value with a String 
Output: 914.56589 
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// working of valueOf() methods
class ValueOfExa {
    public static void main(String arg[])
    {
        int iNum = 30;

        double fNum = 4.56789;
        String s = "91";

        // Returns the string representation of int iNum.
        String sample = String.valueOf(iNum);

        System.out.println(sample);

        // concatenating string with iNum
        System.out.println(sample + s);

        // Returns the string representation of the float
        // fnum.
        sample = String.valueOf(fNum);
        System.out.println(sample);

        // concatenating string with fNum
        System.out.println(s + sample);
    }
}
```

**Output**

```
30
3091
4.56789
914.56789

```

**例 2:**

## Java

```
// Java program to demonstrate
// working of valueOf() methods
class ValueOfExa {
    public static void main(String arg[])
    {
        char[] data
            = { 'G', 'E', 'E', 'K', 'S', ' ', 'F', 'O',
                'R', ' ', 'G', 'E', 'E', 'K', 'S' };
        String sample;

        // Returns the string representation
        // of a specific subarray of the chararray argument
        sample = String.valueOf(data, 0, 15);

        System.out.println(sample);

        // Returns the string of charArray 0 to 5
        sample = String.valueOf(data, 0, 5);

        System.out.println(sample);

        // Returns the string of charArray starting
        // index 6 and total count from 6 is 8
        sample = String.valueOf(data, 6, 8);

        System.out.println(sample);
    }
}
```

**输出**

```
GEEKS FOR GEEKS
GEEKS
FOR GEEK

```

**例 3:**

```
Input :Geeks for Geeks
// check if String value contains a 
// specific string by method contains("Geeks");
Output:true
```

## Java

```
// The following example shows the
// usage of <strong>valueOf(boolean sta)</strong method.
public class StringValueOfBoolean {
    public static void main(String[] args)
    {
        // declare a String
        String data = "Geeks for Geeks";

        // check if String value contains a specific string
        boolean bool = data.contains("Geeks");

        // print the string equivalent of our boolean check
        System.out.println(String.valueOf(bool));
    }
}
```

**输出**

```
true

```

**Java 中 parseInt 和 valueOf 的区别**

整型值的应用编程接口确实说字符串的解释就像它被赋予整型参数一样。但是，valueOf(String) **返回一个新的 Integer()对象，而 parsent(String)返回一个基元 Int。**