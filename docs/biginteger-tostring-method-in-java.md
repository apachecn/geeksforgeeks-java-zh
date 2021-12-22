# Java 中的 BigInteger toString()方法

> 原文:[https://www . geesforgeks . org/big integer-tostring-method-in-Java/](https://www.geeksforgeeks.org/biginteger-tostring-method-in-java/)

BigInteger 类为 toString()提供了 2 种方法。

*   **toString(int radix)**: The java.math.BigInteger.toString(int radix) method returns the decimal String representation of this BigInteger in given radix. Radix parameter decides on which number base (Binary, octal, hex etc) it should return the string. In case of toString() **the radix is by Default 10.** If the radix is outside the range of Character.MIN_RADIX to Character.MAX_RADIX inclusive, it will default to 10.

    **语法:**

    ```
    public String toString(int radix)
    ```

    **参数:**该方法接受单个强制参数**基数**，即字符串表示的基数。

    **返回值:**这个方法返回给定基数下这个大整数的十进制字符串表示。

    **示例:**

    ```
    Input: BigInteger1=321456 radix =2
    Output: 1001110011110110000
    Explanation: BigInteger1.toString(2)=1001110011110110000\. 
    when radix is 2 then function will first convert the BigInteger 
    to binary form then it will return String representation of that binary number.

    Input: BigInteger1=321456 radix=16
    Output: 4e7b0
    Explanation: BigInteger1.toString()=4e7b0\. 
    when radix is 16 then function will first convert the BigInteger 
    to hexadecimal form then it will return String representation of that hexadecimal number.

    ```

    下面的程序说明了 BigInteger 类的 toString(int 基数)方法:

    **例 1:** 当基数= 2 时。意思是二进制形式的字符串。

    ```
    // Java program to demonstrate
    // toString(radix) method of BigInteger

    import java.math.BigInteger;

    public class GFG {

        public static void main(String[] args)
        {

            // Creating BigInteger object
            BigInteger b1;
            b1 = new BigInteger("321456");

            // create radix
            int radix = 2;

            // apply toString(radix) method
            String b1String = b1.toString(radix);

            // print String
            System.out.println("Binary String of BigInteger "
                               + b1 + " is equal to " + b1String);
        }
    }
    ```

    **Output:**

    ```
    Binary String of BigInteger 321456 is equal to 1001110011110110000

    ```

    **例 2:** 当基数= 8 时，表示八进制字符串

    ```
    // Java program to demonstrate 
    // toString(radix) method of BigInteger

    import java.math.BigInteger;

    public class GFG {

        public static void main(String[] args)
        {

            // Creating BigInteger object
            BigInteger b1;
            b1 = new BigInteger("34567876543");

            // create radix
            int radix = 8;

            // apply toString(radix) method
            String b1String = b1.toString(radix);

            // print String
            System.out.println("Octal String of BigInteger "
                              + b1 + " is equal to " + b1String);
        }
    }
    ```

    **Output:**

    ```
    Octal String of BigInteger 34567876543 is equal to 401431767677

    ```

    **例 3:** 当基数= 16 时，表示十六进制形式的字符串

    ```
    // Java program to demonstrate toString(radix) method of BigInteger

    import java.math.BigInteger;

    public class GFG {

        public static void main(String[] args)
        {

            // Creating BigInteger object
            BigInteger b1;
            b1 = new BigInteger("8765432123456");

            // create radix
            int radix = 16;

            // apply toString(radix) method
            String b1String = b1.toString(radix);

            // print String
            System.out.println("Hexadecimal String of BigInteger "
                               + b1 + " is equal to " + b1String);
        }
    }
    ```

    **Output:**

    ```
    Hexadecimal String of BigInteger 8765432123456 is equal to 7f8dc77d040

    ```