# 将二进制转换为八进制的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到转换-二进制到八进制/](https://www.geeksforgeeks.org/java-program-to-convert-binary-to-octal/)

一个**二进制数系统**由两个符号组成:0(0)和 1(1)，分别代表数字电子中的低或**关**和高或**开**状态。它主要是一个基数为 2 的数字系统，在计算机科学中也被广泛使用。所有的数据都存储在计算机中的二进制符号中，也称为位。二进制系统之所以得名，是因为它仅由两个符号组成。二进制数也可以认为是一串 0 和 1

一个**八进制数字系统**包括从 **0 到 7** 的八位数。它的名字来源于它由八个数字组成的事实(因此是十月)，这意味着八。它是一个 8 基数的数字系统，可以通过将二进制数中的位分成三组，并在结果八进制数中将每组的相应值计算为一个数字来表示。

**示例:**

```
Input : 100100
Output: 44

Input : 1100001
Output : 141
```

在本文中，我们将探讨将二进制数转换为八进制数的两种方法。这些方法如下:

*   使用 Java 中内置的[**toOctalString()**](https://www.geeksforgeeks.org/integer-tooctalstring-method-in-java/)**方法**
*   **将二进制数转换成十进制数，十进制数再转换成相应的八进制数。**

****方法 1:****

**使用这种方法，我们首先将一个二进制数转换为一个整数，然后使用 java 的**[**toOctalString()**](https://www.geeksforgeeks.org/integer-tooctalstring-method-in-java/)内置方法将其转换为一串八进制数。然后，该字符串再次转换为整数。****

******语法:******

```
**public static String toOctalString(*int num*)**
```

******参数:**该方法接受需要转换为字符串的整数类型的单个参数*数*。****

******返回值:**该函数返回整数参数的字符串表示形式，以 8 为基数。****

******算法:******

1.  ****将二进制数转换成十进制数。****
2.  ****使用 toOctalString()方法将此十进制数转换为八进制数的字符串。****
3.  ****再次将该字符串转换为整数。****

******示例:******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java program to convert binary to octal

class GFG {

    // method to convert binary to decimal
    int binaryToDecimal(long binary)
    {
        // variable to store the decimal number
        int decimalNumber = 0, i = 0;

        // loop to extract the digits of the
        // binary number
        while (binary > 0) {

            // multiplying each digit of binary
            // with increasing powers of 2 towards
            // left
            decimalNumber
                += Math.pow(2, i++) * (binary % 10);

            // dividing the binary by 10
            // to remove the last digit
            binary /= 10;
        }

        // returning the converted decimal number
        return decimalNumber;
    }

    // function to convert decimal to octal
    int decimalToOctal(long binary)
    {

        // variable to store the decimal number
        // returned by the binaryToDecimal()
        int decimalNumber = binaryToDecimal(binary);

        // using the toOctalString() to convert
        // Integer to String of Octal Number
        String octalString
            = Integer.toOctalString(decimalNumber);

        // converting the String of octal number
        // to an Integer
        int octalNumber = Integer.parseInt(octalString);

        // returning the octal number
        return octalNumber;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // calling and printing the decimalToOCtal
        // method
        System.out.println("octal number:"+ob.decimalToOctal(100100));
    }
}**
```

******Output**

```
octal number:44
```**** 

******方法 2:******

****使用这种方法，我们首先将二进制数转换成十进制数。然后，我们通过连续提取余数并除以 8，将这个十进制数转换为八进制数。****

******算法:******

1.  ****将二进制数转换成十进制数。****
2.  ****现在，对于这个转换后的十进制数，运行一个 while 循环，直到这个数变成 0。****
3.  ****在循环的每次迭代中，通过将数字除以 8 得到余数。****
4.  ****将这个余数乘以 10 的递增幂。****
5.  ****最后将原数除以 8。****

******示例:******

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```
**// Java program to convert binary to octal

class GFG {

    // function to convert binary number
    // to decimal number
    int binaryToDecimal(long binary)
    {

        // variable to store the converted
        // decimal number
        int decimalNumber = 0, i = 0;

        // loop to convert binary to decimal
        while (binary > 0) {

            // extracting every digit of the
            // binary and multiplying with
            // increasing powers of 2
            decimalNumber
                += Math.pow(2, i++) * (binary % 10);

            // dividing the number by 10
            // to remove the last digit
            binary /= 10;
        }

        // returning the converted decimal
        // number
        return decimalNumber;
    }

    // function to convert decimal number
    // to octal
    int decimalToOctal(long binary)
    {

        // variable to store the octal number
        int octalNumber = 0, i = 0;

        // variable to store the output
        // returned by the binaryToDecimal()
        int decimalNumber = binaryToDecimal(binary);

        // loop to convert decimal to octal
        while (decimalNumber != 0) {

            // extracting the remainder on
            // multiplying by 8 and
            // dividing that with increasing
            // powers of 10
            octalNumber += (decimalNumber % 8)
                           * ((int)Math.pow(10, i++));

            // removing the last digit by
            // dividing by 8
            decimalNumber /= 8;
        }

        // returning the converted octal number
        return octalNumber;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        // calling and printing the
        // decimalToOctal() function
        System.out.println(ob.decimalToOctal(1001001));
    }
}**
```

******Output**

```
111
```****