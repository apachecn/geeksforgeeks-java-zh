# Java 中的十二进制

> 原文:[https://www.geeksforgeeks.org/duodecimal-in-java/](https://www.geeksforgeeks.org/duodecimal-in-java/)

十二进制表示一种记数系统，其中以 12 为基数的数称为十二进制数。在 java 中，我们可以使用将十二进制数转换成相应的二进制、八进制、十进制、十六进制数或任何其他基数。在 java 中，我们可以使用预定义的包或用户定义的方法来执行以下转换。

让我们将十二点对话的几个样本集描绘成其他基本数字，如下所示:

> (15b) <sub>12</sub> 的**十二进制数转换为**二进制数(11010111) <sub>2</sub>****
> 
> (182)12 的**十二进制数转换为**八进制数(362)8****
> 
> (262)12 的**十二进制数转换为**十进制数(362)10****
> 
> (288052)12 的**十二进制数转换为**十六进制数(A563E)16****
> 
> (58576a2)12 的**十二进制数转换为**六进制数(A563E)32****

**程序:**

转换为十二进制数需要某些步骤，如下所示:

1.  取一个十六进制数作为用户输入。
2.  创建用户定义的函数，将其转换为十进制数。
3.  创建另一个用户定义的函数，将十进制数转换为十二进制数。
4.  打印结果十二进制数。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program Illustrating DuodecimalNumber via Conversion
// of Hexadecimal Numbers into Duodecimal Numbers

// Importing utility classes
import java.util.*;

// Main class
// Representing equivalent duodecimal No of Hexadecimal No
class Main {

    // Method 1
    // Returning the decimal number of the given hexadecimal
    // number
    public static String
    convertToDec(String value, int base,
                 Map<Character, Integer> hexatoDec)
    {

        int sum = 0;
        int pow = 0;
        String tempData = value;

        // Logic to find equivalent decimal number
        for (int i = tempData.length() - 1; i >= 0; i--) {

            // charAt() represents element at 'i'th index
            int val = tempData.charAt(i) - '0';

            if (base == 16
                && hexatoDec.containsKey(
                    tempData.charAt(i))) {
                val = hexatoDec.get(tempData.charAt(i));
            }

            // Math.pow() calculates x^n
            sum += (val) * (Math.pow(base, pow++));
        }

        return String.valueOf(sum);
    }

    // Method 2
    // Converting decimal number into Duodecimal number and
    // return it into main() method.
    public static String
    convertToDuoDecimal(String value, int base,
                        Map<Integer, Character> dectoHex,
                        Map<Character, Integer> hextoDec)
    {

        String val = value;
        int newBase = base;

        // Checks whether the base is decimal or not
        if (newBase != 10) {

            // If the base is not 10, it call the
            // convertToDec() method which return the
            // corresponding decimal number of the given
            // number.
            val = convertToDec(value, base, hextoDec);

            // After converting the number, new base is
            // updated Say be it 10
            newBase = 10;
        }

        // Converting the string number into integer
        // using parseInt()
        int temp = Integer.parseInt(val);
        int rem;
        String duoDecimal = "";

        // Creating duoDecimalChars[] array for defining the
        // characters
        char duoDecimalChars[]
            = { '0', '1', '2', '3', '4', '5',
                '6', '7', '8', '9', 'A', 'B' };

        // Logic to find equivalent duodecimal number
        while (temp > 0) {

            rem = temp % 12;
            duoDecimal = duoDecimalChars[rem] + duoDecimal;
            temp = temp / 12;
        }
        return duoDecimal;
    }

    // Method 3
    // Main driver method
    public static void main(String[] args)
    {

        // Createing a variable to store hexadecimal number
        String val;

        // Custom input in main() for hexadecimal number
        val = "3A4C2";

        // Creating a hexatoDec and dectoHexa for storing
        // values by creating object of Map class Declaring
        // object of character and integer type
        Map<Character, Integer> hexatoDec = new HashMap<>();
        Map<Integer, Character> dectoHex = new HashMap<>();

        // Logic to store date into hexatoDec and dectoHexa
        // map
        for (int i = 0; i < 6; i++) {
            dectoHex.put(10 + i, (char)('A' + i));
            hexatoDec.put((char)('A' + i), 10 + i);
        }

        // Call the convertToDuoDecimal() and printing the
        // returned value of it.
        System.out.println(
            "Duodecimal : "
            + convertToDuoDecimal(val, 16, dectoHex,
                                  hexatoDec));
    }
}
```

**Output**

```java
Duodecimal : B622A
```