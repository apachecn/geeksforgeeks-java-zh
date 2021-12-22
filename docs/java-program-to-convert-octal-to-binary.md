# 将八进制转换为二进制的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序转八进制转二进制/](https://www.geeksforgeeks.org/java-program-to-convert-octal-to-binary/)

给定一个八进制数作为输入，任务是将该数转换成它的二进制等价数。

**示例:**

```
Input: Octal Number = 513
Output: Binary equivalent value is: 101001011

Explanation : 
Binary equivalent value of 5: 101
Binary equivalent value of 1: 001

Binary equivalent value of 3: 011
```

**八进制数字系统:**

八进制数字系统是以 8 为基数的位置数字系统，使用八个不同的数字 0 到 7。

**二进制数系统:**

二进制数是用基数为 2 的二进制数字系统表示的数，它只使用两个符号:0 和 1。

**八进制到二进制转换表:**

<figure class="table">

| 八进制的 | 二进制的 |
| --- | --- |
| Zero | 000 |
| one | 001 |
| Two | 010 |
| three | 011 |
| four | One hundred |
| five | One hundred and one |
| six | One hundred and ten |
| seven | One hundred and eleven |

</figure>

**方法 1:天真方法**

在这种方法中，八进制数的输入将被视为一个字符串。此外，完整的字符串将一个字符一个字符地迭代，并为每个字符(即。，八进制数字)，它的等价二进制值根据上面的八进制到二进制转换表将被求值。每次迭代的结果将被添加到结果字符串中，所有值的组合将给出所需的二进制数。下面是这个方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert
// Octal number to Binary

class OctalToBinary {

    // function to convert octal number
    // to its binary equivalent value
    static String converter(String octalValue)
    {

        // integer variable to iterate
        // the input octal string
        int i = 0;

        // string to store the result
        String binaryValue = "";

        // iterating the complete length
        // of octal string and assigning
        // the equivalent binary value
        // for each octal digit
        while (i < octalValue.length()) {

            // storing character according
            // to the number of iteration
            char c = octalValue.charAt((int)i);

            // switch case to check all
            // possible 8 conditions
            switch (c) {
            case '0':
                binaryValue += "000";
                break;
            case '1':
                binaryValue += "001";
                break;
            case '2':
                binaryValue += "010";
                break;
            case '3':
                binaryValue += "011";
                break;
            case '4':
                binaryValue += "100";
                break;
            case '5':
                binaryValue += "101";
                break;
            case '6':
                binaryValue += "110";
                break;
            case '7':
                binaryValue += "111";
                break;
            default:
                System.out.println(
                    "\nInvalid Octal Digit "
                    + octalValue.charAt((int)i));
                break;
            }
            i++;
        }

        // returning the final result
        return binaryValue;
    }

    // Driver code
    public static void main(String args[])
    {

        System.out.println("Octal to Binary Conversion\n");

        // octal number which is to be converted
        String octalNumber = "315";
        System.out.println("Octal number: " + octalNumber);

        // calling the converter method and
        // storing the result in a string variable
        String result = converter(octalNumber);

        System.out.println("Binary equivalent value is: "
                           + result);
    }
}
```

**Output**

```
Octal to Binary Conversion

Octal number: 315
Binary equivalent value is: 011001101
```

**方法二:数学方法**

这种方法包括完整的数学计算，以获得所需的结果。八进制数的输入将被视为整数。此外，首先将其转换为十进制等值，然后使用数学运算将其从十进制数转换为二进制等值。下面是这个方法的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert
// Octal number to Binary
public class OctalToBinary {

    // function to convert octal number
    // to its binary equivalent value
    public static int converter(int octalValue)
    {

        // declaring all variable
        // to store the intermediate results
        int i = 0;
        int decimalValue = 0;
        int binaryValue = 0;

        // converting octal number
        // into its decimal equivalent
        while (octalValue != 0) {
            decimalValue
                += (octalValue % 10) * Math.pow(8, i);
            ++i;
            octalValue /= 10;
        }

        i = 1;

        // converting generated decimal number
        // to its binary equivalent
        while (decimalValue != 0) {
            binaryValue += (decimalValue % 2) * i;
            decimalValue /= 2;
            i *= 10;
        }

        // returning the final result
        return binaryValue;
    }

    // Driver code
    public static void main(String[] args)
    {

        System.out.println("Octal to Binary Conversion\n");

        // octal number which is to be converted
        int octalNumber = 315;
        System.out.println("Octal number: " + octalNumber);

        // calling the converter method and
        // storing the result in a string variable
        int result = converter(octalNumber);

        // printing the binary equivalent value
        System.out.println("Binary equivalent value is: "
                           + result);
    }
}
```

**Output**

```
Octal to Binary Conversion

Octal number: 315
Binary equivalent value is: 11001101
```

**方法 3:使用内置的 java 方法**

[integer . parsent()](https://www.geeksforgeeks.org/string-to-integer-in-java-parseint/)是 Java 中的内置函数，用于将字符串解析为由基数值(方法的第二个参数)指定的数字系统。在这种方法中，八进制数的输入将被视为字符串。八进制字符串将被解析为八进制的整数值。此外，八进制数将使用另一种内置方法[将其转换为等效的二进制数。结果值也将是字符串数据类型。下面是实现。](https://www.geeksforgeeks.org/java-lang-integer-tobinarystring-method/)

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert
// Octal number to Binary
class OctalToBinary {

    // function to convert octal number
    // to its binary equivalent value
    public static String converter(String octalValue)
    {

        // parsing the string value
        // by following octal number system
        int octal = Integer.parseInt(octalValue, 8);

        // converting octal number to binary
        // and storing as a string
        String binaryValue = Integer.toBinaryString(octal);

        // returning the resultant string
        return binaryValue;
    }

    // Driver code
    public static void main(String args[])
    {

        System.out.println("Octal to Binary Conversion\n");

        // octal number which is to be converted
        String octalNumber = "315";
        System.out.println("Octal number: " + octalNumber);

        // calling the converter method and
        // storing the result in a string variable
        String result = converter(octalNumber);

        // printing the binary equivalent value
        System.out.println("Binary equivalent value is: "
                           + result);
    }
}
```

**Output**

```
Octal to Binary Conversion

Octal number: 315
Binary equivalent value is: 11001101
```