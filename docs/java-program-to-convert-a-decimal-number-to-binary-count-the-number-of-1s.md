# 将十进制数转换为二进制数的 Java 程序&计算 1 的个数

> 原文:[https://www . geesforgeks . org/Java-program-convert-a-decimal-number-to-binary-count-of-1s/](https://www.geeksforgeeks.org/java-program-to-convert-a-decimal-number-to-binary-count-the-number-of-1s/)

根据数字系统，默认计算是对十进制数进行的，十进制数的基数标准化为 10。机器在 0 和 1 中计算物理层的所有执行。因此需要一种以 2 为基数的数字系统，称为二进制数字系统。二进制数可以转换成十进制数，反之亦然。在 java 中，有 4 种类型的数字:

<figure class="table">

| 数字的类型 | 基础 |
| --- | --- |
| 二进制的 | Two |
| 八进制十进制 | eight |
| 小数 | Ten |
| 十六进制的 | Sixteen |

</figure>

**方法:**在 Java 中，有两种方法可以转换，要么使用预定义的方法，要么使用三级逻辑构建，如下所示:

1.  **使用** [***整数***](https://www.geeksforgeeks.org/java-lang-integer-tobinarystring-method/) 方法(整数包装类)
2.  **使用蛮力方法**(不使用任何预定义的类)

**示例:**

```java
Input. 1: 10
Output 1: The binary equivalent of 10 is : 1010
          Number of 1s is : 2

Input  2: 15
Output 2: The binary equivalent of 15 is : 1111
          Number of 1s is 4

```

**方法 1:使用**[**toBinaryString()**](https://www.geeksforgeeks.org/java-lang-integer-class-methods/)**方法:**表示要转换为二进制的数字。**Java 的 Integer 类提供了一些处理 Integer 的有用方法。其中一种方法是[*integer . tobinarystring(int x)*](https://www.geeksforgeeks.org/java-lang-integer-tobinarystring-method/)**

******语法:******

```java
**public static String toBinaryString(int variable_name)**
```

******参数:**待转换的十进制整数。****

******返回类型:**字符串，它将转换后的整数的二进制表示或整数的简单二进制等价表示作为字符串对象。****

******异常:**这个方法没有抛出异常****

******参数:**取一个整型(或整型)参数****

******实现:**要计算 1 的个数，检查得到的二进制字符串的每个字符是否等于 1。****

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java program to convert decimal to binary number
// and counting number of 1's in it

public class GFG {

    // Function to convert decimal to binary
    void convertAndCount(int num)
    {
        // Store the count of 1s currently 0
        int count = 0;

        // Returns a String object representing
        // binary equivalent of passed decimal number
        String binary = Integer.toBinaryString(num);

        // Iterating over obtained string using length
        // function
        for (int i = 0; i < binary.length(); i++)

            // Checking 1 is present in binary
            if (binary.charAt(i) == '1')

                // Increment the count
                // if any char equals 1
                count++;

        // Printing the binary equivalent
        System.out.println("The binary equivalent of " + num
                           + " is : " + binary);

        // Printing the no of 1 in above binary number
        System.out.println("Number of 1s is : " + count);
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Creating object in main
        GFG obj = new GFG();

        // Calling the convertAndCount() method
        // over the integer value 18
        obj.convertAndCount(18);
    }
}**
```

******Output**

```java
The binary equivalent of 18 is : 10010
Number of 1s is : 2
```**** 

******方法 2:不使用预定义变量******

*   ****将要转换成二进制的十进制数除以 2****
*   ****存储剩余部分****

## ****Java 语言(一种计算机语言，尤用于创建网站)****

```java
**// Java program to convert decimal to binary number
// and counting number of 1's in it

public class GFG {

    // Function to convert decimal to binary
    void convertAndCount(int num)
    {
        int temp = num; // a temporary variable to store the
                        // value of num

        // to store the binary value
        int[] binary = new int[20];

        // to store the count of 1s
        int count = 0;
        int i;

        // to iterate through the loop and keep a
        // count of no.of digits in the obtained binary
        for (i = 0; temp > 0; i++) {

            // divide the number by 2
            // and store the remainder
            temp /= 2;
            binary[i] = temp % 2;

            // If 1 is present in binary
            if (binary[i] == 1)

                // increment the count if any digit
                // is equal to 1
                count++;
        }

        // Printing binary of decimal number
        System.out.print("The binary equivalent of " + num
                         + " is : ");

        // Iterating over array
        for (int j = i - 1; j >= 0; j--)

            // Printing obtained array in reverse order
            System.out.print(binary[j]);

        // Printing number of 1's
        System.out.println("\nNumber of 1s is : " + count);
    }

    // Main driver method
    public static void main(String[] args)
    {
        // Creating class GFG object in main
        GFG obj = new GFG();

        obj.convertAndCount(18);
        // calling convertAndCount() method on decimal
        // over the value 18
    }
}**
```

******Output**

```java
The binary equivalent of 18 is : 01001
Number of 1s is : 2
```****