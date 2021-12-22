# 用递归求一个数的倒数的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-reverse-of-number-use-recursion/](https://www.geeksforgeeks.org/java-program-to-find-reverse-of-a-number-using-recursion/)

[递归](https://www.geeksforgeeks.org/recursion/)是一个函数反复调用自己，直到落在基础条件下，我们的动机达到的过程。

要使用递归解决任何问题，我们只需遵循以下步骤:

1.  从与较大/原始问题相似的问题中假设较小的问题。
2.  决定最小有效输入或最小无效输入的答案，作为我们的基本条件。
3.  逼近解，将答案与递归函数给出的较小问题联系起来，用它找到较大/原始问题的答案。

**示例:**

```
Input:  14689
Output: 98641

Input:  7654321
Output: 1234567
```

**方法 1:**

*   在这种方法中，我们可以简单地打印一个数字的单位数字。
*   然后在去掉这个单位数字(number/10)后调用这个数字的递归函数
*   这个过程一直持续到数字减少到一位数。

**示例:**

```

    num = 82695
        reverse(82695)
           |
           |__print(5)
              reverse(8269)
                    |
                    |__print(9)
                       reverse(826)
                            |
                            |__print(6)
                               reverse(82)
                                   |
                                   |__print(2)
                                      reverse(8)
                                          |
                                          |__print(8)
                                             return
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to reverse
// an integer recursively
class GFG {

    // Recursive function to print
    // the number in reversed form
    public static void Reverse(int num)
    {

        // base condition to end recursive calls
        if (num < 10) {
            System.out.println(num);
            return;
        }

        else {

            // print the unit digit of the given number
            System.out.print(num % 10);

            // calling function for remaining number other
            // than unit digit
            Reverse(num / 10);
        }
    }

    // driver code
    public static void main(String args[])
    {
        // number to be reversed
        int num = 98765;

        System.out.print("Reversed Number: ");

        // calling recursive function
        // to print the number in
        // reversed form
        Reverse(num);
    }
}
```

**Output**

```
Reversed Number: 56789
```

**方法 2:**

*   在这种方法中，我们可以简单地维护一个变量，在这个变量中我们可以存储到目前为止颠倒的数字。
*   我们可以这样做:从数字中提取一个单位数字，然后将提取的整数加到反转的数字中
*   但这里的关键因素是，我们必须将反数乘以 10，然后再将提取的数字加到反数上。

**示例:**

```
num = 48291
ans = 0       -> variable to store reversed number

How this works:    
    reverse(num)
          |
          |__ temp = num % 10    -> extracting unit digit from nnumber
                ans = ans*10 + temp   -> adding temp at unit position in reversed number 
          reverse(num/10)    -> calling function for remaining number
Implementation:
          reverse(48291)
                |
                |__ temp=1
                      ans= 0*10 + 1  --> ans=1
                      reverse(4829)
                        |
                       |__ temp=9
                              ans= 1*10 + 9  --> ans=19
                                reverse(482)
                                     |
                                     |__ temp= 2
                                         ans= 19*10 +2  --> ans=192
                                         reverse(48)
                                              |
                                              |__ temp=8
                                                  ans=192*10 + 8  --> ans=1928
                                                  reverse(4)
                                                      |
                                                      |__ temp=4
                                                          ans=1928*10 +4 --> ans=19284
                                                          reverse(0)
                                                              |
                                                              |__ return ans

```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to reverse an integer recursively
class GFG {

    // Variable to store reversed
    // number after every
    // recursive call
    static int ans = 0;

    static int Reverse(int var)
    {

        // base condition to end the
        // recursive calling of function
        if (var == 0) {

            // We have reversed the
            // complete number and
            // stored in ans variable
            return ans;
        }

        if (var > 0) {

            // temp variable to store the digit at unit
            // place in the number
            int temp = var % 10;

            // Add this temp variable in the ans variable
            // which stores the number reversed till now
            ans = ans * 10 + temp;

            // recursive calling of function to reverse the
            // remaining number
            Reverse(var / 10);
        }

        // returning final answer when the number is
        // reversed completely
        return ans;
    }

    public static void main(String[] args)
    {

        // Number to be reversed
        int var = 98765;

        // Variable to store reversed number returned by
        // reverse function
        int rev;

        // Calling reverse function and storing the return
        // value in rev variable
        rev = Reverse(var);

        // Printing the Reversed Number
        System.out.println("Reversed number: " + rev);
    }
}
```

**Output**

```
Reversed number: 56789
```

**注意:**发生溢出时，Java 不会抛出异常，因此如果反转数大于 Integer，可能会出现溢出问题。MAX_VALUE *(2147483647)* 在方法 2 中，但是在方法 1 中不会有这样的问题。