# Java 程序使用边做边循环来反转一个数字并找到其数字的总和

> 原文:[https://www . geesforgeks . org/Java-program-to-reverse-a-number-and-find-sum-it-digits-in-do-while-loop/](https://www.geeksforgeeks.org/java-program-to-reverse-a-number-and-find-the-sum-of-its-digits-using-do-while-loop/)

**问题陈述:**该数字应该由用户输入，无论它是位于保存该数字的原始数据类型内的任何随机数。首先，数字需要反转。第二，要使用边做边循环的约束来计算数字的总和。

[**边做边循环**](https://www.geeksforgeeks.org/java-do-while-loop-with-examples/) **:** 现在用户有时确实会在一会儿和一个边做边循环之间混淆。While 循环首先检查条件，然后执行语句，而 Do-while 循环执行语句，然后检查条件。“边做边做”产生的一个要点是，即使条件失败了，它仍然会被执行一次。

![do while loop in Java](img/833b66b2cafc69086aa0c81e2474c988.png)

**边做边循环的语法:**

```
do 
{
 // statement to be executed
}
while(condition check)
```

**边做边循环的使用:**

向用户显示一些菜单换句话说，游戏是这样实现的，目标是向用户显示按 1 做这个，按 2 做那个，以此类推，其中有一个选项按 Q 退出这个游戏。因此，do-while 循环希望至少向用户显示一次菜单。当用户采取行动时，适当的步骤就完成了。因此，虽然条件应该是如果用户按下 Q 退出，菜单在边做边循环中。

**方法:**使用边做边循环，找出一个数的倒数和它的位数之和。输入任何数字作为输入，然后使用模数和除法，运算符反转该特定数字并找到其数字的总和。

**算法:**

1.  从用户处获取号码
2.  创建两个变量，即 reverse_number 和 sum，并将其初始化为 0
3.  反转数字
4.  打印反向号码
5.  打印从较小的总和中获得的数字的最终总和。

**反转算法讨论如下:**

*   将 rev 乘以 10，然后将余数与 reverseNumber 相加。//rem = num % 10；rev = rev * 10+rem；
*   将 rem 添加到当前总和中，以找到数字的总和，并将它们存储在一个变量中，该变量将返回最终总和。Final_sum=current_sum，其中 current_sum=current_sum +余数
*   将数字除以 10，访问数字当前数字前面的数字，如下所示。//num = num/10；while(num > 0)；

**例 1:** 不用做函数就能对数字进行反算和求和的 Java 程序

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to reverse and and sum up digits of number

// Importing generic Classes/Files
import java.io.*;
// Importing Scanner Class
import java.util.Scanner;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // creating vaiables
        int num, rem;

        // Creating variables and initializing at same time
        int rev = 0, sum = 0;

        // Using scanner to take input from user
        // Scanner sc = new Scanner(System.in);

        // Remove comments from lineNo20
        // to take dynamic user input

        // Displaying message
        System.out.println("Enter the number: 25 ");

        // Taking input from user
        // num = sc.nextInt();

        // Hard coded input
        num = 25;

        // Do-while loop for iteration over digits of number
        do {

            // Step1: Modulo with 10 to get last digit
            rem = num % 10;

            // Step2: Reverse the number
            rev = rev * 10 + rem;

            // Sum of the digits of number
            sum = sum + rem;

            // Step3: Dividing number by 10 to loose last
            // digit
            num = num / 10;
        }

        // Condition check
        // Remember: By this time 1 iteration is over even
        // if conditions false
        while (num > 0);

        // Printing the reverse number
        System.out.println("Reverse of given number: "
                           + rev);

        // Summing up digits of number as shown in above
        // steps
        System.out.println("Sum of digits of given number: "
                           + sum);
    }
}
```

**Output**

```
Enter the number: 25 
Reverse of given number: 52
Sum of digits of given number: 7
```

**示例 2:** 在此示例中，通过创建 do-while 循环的函数以及稍后在主驱动程序方法中调用它们，分别显示了 do-while 循环。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

// Importing specific Scanner Class to show menu
import java.util.Scanner;

class GFG {

    // Iterative function to reverse digits of number
    // static int reversDigits(int num)

    // Hardcoded input where input number equals 25
    static int reversDigits(int num)
    {

        // Making input hard coded else
        num = 25;
        // else do not initialize num

        // creating and Initialising reverseNo with 0
        // Creating remainder variable
        int rev = 0, rem;

        // Statements to be executed in do loop
        do {
            // Reversal of a number as discussed in
            // algorithm
            rem = num % 10;
            rev = rev * 10 + rem;
            num = num / 10;

        }

        // Condition check
        while (num > 0);

        // Returning reverse of the user enter number
        return rev;
    }

    // Iterative function findingsum of the digits of number
    // static int sumDigits(int num)

    // Hardcoded input where input number equals 25
    static int sumDigits(int num)
    {
        // Making input hard coded
        num = 25;
        // else do not initialize num

        // creating and Initialising final_sum with 0
        // Creating remainder variable
        int sum = 0, rem;

        // Statements to be executed in do loop
        do {
            // Retrieving steps as discussed in above 3
            // steps
            rem = num % 10;
            sum = sum + rem;
            num = num / 10;

        }
        // condition check
        while (num > 0);

        // Returning Sum of digits of a reversed number
        return sum;
    }

    // Main driver method
    public static void main(String[] args)
    {
        // declaring variable to store user entered number
        // int num;

        // Scanner Class to read the entered number

        // Commented out to hard code the input
        // else remove comments
        // Scanner sc = new Scanner(System.in);

        // Input is hardcoded for display
        // else remove comments from line no 77

        // Considering hard coded input
        int num = 25;

        // Printing message
        System.out.println(num);

        // Taking input from user
        // Making input hard coded else
        // remove comments from line no 82
        // num = sc.nextInt();

        // Calling above functions to print reversed number
        System.out.println("Reverse of given number: "
                           + reversDigits(num));

        // Calling above functions to print reversed number
        System.out.println("Sum of digits of given number: "
                           + sumDigits(num));
    }
}
```

**Output**

```
25
Reverse of given number: 52
Sum of digits of given number: 7
```