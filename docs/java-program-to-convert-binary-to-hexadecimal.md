# 将二进制转换为十六进制的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到转换-二进制到十六进制/](https://www.geeksforgeeks.org/java-program-to-convert-binary-to-hexadecimal/)

**十六进制**数字系统顾名思义由 16 个实体组成。这 16 个实体由 **10 位数字组成，0-9** 也代表十六进制系统的前 10 位数字。对于剩下的 6 个数字，我们使用从 **A 到**的英文字母来表示数字 10 到 15。应该注意的是，十六进制系统中最低的数字是 0，最高的是 15，用 f 表示。十六进制数可以通过将 4 个数字组合成十六进制数的单个字符而从二进制数中导出。

**示例:**

```java
Input: 11011111
Output: DF

Input: 10001101
Output: 8D
```

*   在上面的例子中，二进制数 10001101 可以分解成 4 位的**块**，例如 1000 和 1101，它们作为对应的十六进制数的 2 个字符。
*   所得的十六进制数将是 8D，其中每个字符都是通过计算其在十进制系统中的相应值来确定的，如果它是两位数，则用字母表来替换它，在这种情况下，D 代表 13。十六进制系统也称为**基数-16。**

对于二进制到十六进制的转换，我们将使用以下两种方法:

1.  使用**至**内置 java 方法
2.  重复获取余数，并将转换后的十进制数除以 16

**方法 1:**

使用这种方法，我们首先将二进制数转换成存储为整数的十进制数。然后，我们简单地使用 java 的[**to exstring()**](https://www.geeksforgeeks.org/java-lang-integer-tohexstring-method-examples/)方法来生成想要的输出字符串。

**语法:**

```java
public static String toHexString(int num)
```

**参数:**

*   **数字**–该参数指定将
    转换为十六进制字符串的数字。数据类型是 int。

**返回值:**该函数返回 int 参数的字符串表示形式，以 16 为底的无符号整数表示。

**算法:**

1.  将二进制数转换成十进制数。
2.  要将二进制数转换为十进制数，首先，通过用除以 10 得到余数来提取每个数字。
3.  接下来，将这个数字乘以 2 的递增幂。
4.  继续将原始二进制数除以 10，以消除每次迭代中的最后一个数字。
5.  得到十进制数后，只需使用 toHexString()方法就可以得到想要的输出。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert binary to hexadecimal

class GFG {

    // method to convert binary to decimal
    int binaryToDecimal(long binary)
    {

        // variable to store the converted
        // binary number
        int decimalNumber = 0, i = 0;

        // loop to extract the digits of the binary
        while (binary > 0) {

            // extracting the digits by getting
            // remainder on dividing by 10 and
            // multiplying by increasing integral
            // powers of 2
            decimalNumber
                += Math.pow(2, i++) * (binary % 10);

            // updating the binary by eliminating
            // the last digit on division by 10
            binary /= 10;
        }

        // returning the decimal number
        return decimalNumber;
    }

    // method to convert decimal to hexadecimal
    String decimalToHex(long binary)
    {
        // variable to store the output of the
        // binaryToDecimal() method
        int decimalNumber = binaryToDecimal(binary);

        // converting the integer to the desired
        // hex string using toHexString() method
        String hexNumber
            = Integer.toHexString(decimalNumber);

        // converting the string to uppercase
        // for uniformity
        hexNumber = hexNumber.toUpperCase();

        // returning the final hex string
        return hexNumber;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        long num = 10011110;

        // calling and printing the output
        // of decimalToHex() method
        System.out.println("Inputted number : " +num);
        System.out.println(ob.decimalToHex(10011110));
    }
}
```

**Output**

```java
Inputted number : 10011110
9E
```

**方法 2:**

*   在第二种方法中，我们再次首先将二进制数转换为十进制数。
*   然后我们不断地除，得到这个十进制数的余数，得到原始二进制数中每组 4 位的单个字符。

**算法:**

1.  使用上述算法中的步骤 2-4 将二进制转换为十进制。
2.  接下来，运行 while 循环，终止条件是十进制数变为 0，更新条件是在每次迭代中十进制数除以 16。
3.  在每次迭代中，用 16 除这个数得到余数。
4.  组成一个新的字符串，并继续添加剩余的字符除以 16。
5.  如果余数大于或等于 10，根据余数用字母 A-F 替换。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to convert binary to hexadecimal

class GFG {

    // method to convert binary to decimal
    int binaryToDecimal(long binary)
    {

        // variable to store the converted binary
        int decimalNumber = 0, i = 0;

        // loop to extract digits of the binary
        while (binary > 0) {

            // extracting each digit of the binary
            // by getting the remainder of division
            // by 10 and multiplying it by
            // increasing integral powers of 2
            decimalNumber
                += Math.pow(2, i++) * (binary % 10);

            // update condition of dividing the
            // binary by 10
            binary /= 10;
        }

        // returning the decimal
        return decimalNumber;
    }

    // method to convert decimal to hex
    String decimalToHex(long binary)
    {

        // variable to store the output of
        // binaryToDecimal() method
        int decimalNumber = binaryToDecimal(binary);

        // character array to represent double
        // digit remainders
        char arr[] = { 'A', 'B', 'C', 'D', 'E', 'F' };

        // variable to store the remainder on
        // division by 16
        int remainder, i = 0;

        // declaring the string that stores the
        // final hex string
        String hexNumber = "";

        // loop to convert decimal to hex
        while (decimalNumber != 0) {

            // calculating the remainder of decimal
            // by dividing by 16
            remainder = decimalNumber % 16;

            // checking if the remainder is >= 10
            if (remainder >= 10)

                // replacing with the corresponding
                // alphabet from the array
                hexNumber = arr[remainder - 10] + hexNumber;

            else

                hexNumber = remainder + hexNumber;

            // update condition of dividing the
            // number by 16
            decimalNumber /= 16;
        }

        // returning the hex string
        return hexNumber;
    }

    // Driver Code
    public static void main(String[] args)
    {

        // instantiating the class
        GFG ob = new GFG();

        long num =11000011;

        // printing and calling the
        // decimalToHex() method
        System.out.println("Input : "+num);
        System.out.println("Output : " +ob.decimalToHex(num));
    }
}
```

**Output**

```java
Input : 11000011
Output : C3
```